1.两数之和
https://leetcode-cn.com/problems/two-sum/

``` javascript
var twoSum = function(nums, target){
    const map = new Map();
    for(let i=0; i<nums.length; i++){
        if (map.has(nums[i])){
            return [map.get(nums[i]),i];
        }else{
            map.set(target-nums[i],i);
        }
    }
}
```
