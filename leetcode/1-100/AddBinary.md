# Add Binary
tip:二进制相加算法
## 示例代码
``` java
class Solution {
    public String addBinary(String a, String b) {
        int i = a.length()-1, j = b.length()-1;
        int carry  = 0;

        StringBuilder stringBuilder = new StringBuilder();
        while (i >= 0 || j >= 0) {
            int sum = carry;
            if (i >= 0) {
                sum += a.charAt(i--) - '0';
            }
            if (j >= 0) {
                sum += b.charAt(j--) - '0';
            }
            stringBuilder.append(sum%2);
            carry = sum/2;
        }
        if (carry == 1) stringBuilder.append(carry);
        return stringBuilder.reverse().toString();
    }
}
```
