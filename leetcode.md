## 204. Count Primes
注意全部初始化为1不能： 
bool boolArray[ARRAY_SIZE] = { 1 } 
这样只会把第一个bool值初始化为true，其他都是false；

可以这样： 
std::fill_n(FcpNumberIsOk, MAX_FCPS, true);

选质数有一个较高效的算法。
```
class Solution {
public:
    int countPrimes(int n) {
        bool prime[n+10] = {0};
        int count = 0;
        int i=2;
        for(i=2;i<=n;i++){
            if(prime[i]){
                continue;    
            }
            count++;
            int j=2*i;
            while(j<=n){
                prime[j] = true;
                j+=i;
            }
        }
        return count;
    }
};
```