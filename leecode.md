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

2.可被 5 整除的二进制前缀
https://leetcode-cn.com/problems/binary-prefix-divisible-by-5/

```javascript
/**
 * @param {number[]} A
 * @return {boolean[]}
 */
var prefixesDivBy5 = function (A) {
  if (A && A.length) {
    let temp = 0;
    const result = A.map(a => {
      temp = ((temp << 1) + a) % 5;
      return temp === 0;
    });
    return result;
  }
  return [];
};
```
主要技巧为移位运算及取模运算，一开始直接拼接字符串，再parseInt(str,2) 发现溢出了导致计算出错，所以只能进行移位运算，并且还只能取余数
