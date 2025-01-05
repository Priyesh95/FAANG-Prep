## Two Sum solution

```bash
seen = {}
for i,num in enumerate(nums):
     k = target - num
     if k in seen:
         return [seen[k],i]
     else:
         seen[num] = i
```

## Maximum Subarray

```bash
curr_sum = nums[0]
max_sum = nums[0]

for num in nums[1:]:
  curr_sum = max(curr_sum + num, num)
  max_sum = max(curr_sum,max_sum)
return max_sum
```

## Product of Array Except Self

```bash
forward_prod = []
curr_prod = 1
for num in nums:
  curr_prod *= num
  forward_prod.append(curr_prod)

curr_prod = 1
backward_prod = []
i = len(nums) - 1
while i >= 0:
  curr_prod *= nums[i]
  backward_prod.insert(0,curr_prod)
  i-=1


output = [backward_prod[1]]
i = 1
while i < len(nums)-1:
  output.append(forward_prod[i-1]*backward_prod[i+1])
  i+=1
output.append(forward_prod[i-1])
return output

```


