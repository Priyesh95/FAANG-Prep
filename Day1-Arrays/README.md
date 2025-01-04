## Two Sum solution

```bash
seen = {}
for i,num in enumerate(nums):
     k = target - num
     if k in seen:
         return [seen[k],i]
     else:
         seen[num] = i


