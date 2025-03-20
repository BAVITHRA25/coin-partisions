# coin-partisions
MOD = 10**9 + 7
p = [1]+[0]*60000
g = lambda k,s: k*(3*k+s)//2
pent = [g(k,s)for k in range(1,202) for s in(-1,1)]

for n in range(1,60001):
    p[n] = sum(p[n-v] * (1-(k&2)) for k,v in enumerate(pent) if v<=n) % MOD

for _ in range(int(input())):
    print(p[int(input())])
