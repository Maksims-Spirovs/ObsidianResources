Diff from iterative, div&conq, recursive and dynamic programming algorithms
Optimal, making best choice at each step

Given m coins, find minimum amount needed to add up to value m

Naive:
	pick c whose value is >= m:
		min number of coins we can split m into without including c
		min number of coins we can split m into with including c
			return minimum number between both cases

			def coinSplit(m):
				return coinSplitRec(m,0)

			def coinSplitRec(m, i):
				if m == 0: return 0
				if i == len(coin)-1: return m
				without = coinSplitRec(m, i+1)
				if coin[i] <= m:
					with = 1 + coinSplitRec(m-coin[i], i)
					if with < without:
						return with
				return without

Greedy:
	pick c whose value > m
	find minimum number of coins adding up to m-c
	add 1 to it and return it

		coin = [200, 100, 50, 20, 10, 5, 2, 1]

		def coinSplitGD(m):
			return coinSplitGDRec(m, 0)
			
		def coinSplitGDRec(m, i):
			if m==0: return 0
			if i== len(coin)-1: return m
			if coin[i] <= m: return 1 + coinSplitGDRec(m-coin[i],i)
			return coinSplitGDRec(m, i+1)