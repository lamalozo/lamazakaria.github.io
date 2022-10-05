# fibonacci numbers

The sequence of fibonacci numbers may be defined by **recurrence relation** which is equation according to which **nth term** of a sequence of numbers is **equal** to some combination of the previous terms 

Fn = Fn-1 + Fn-2

The Fibonacci numbers are the numbers in the following integer sequence.

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, …….

![Fibonacci_Spiral svg](https://user-images.githubusercontent.com/115074648/194080268-fbf00d7a-6b9e-47cd-8ba1-680a6d5f2f5f.png)

---

## Programs of fibonacci numbers
Given input n , output nth fibonacci number

*Examples*
- input = 2 , output = 1
- input = 7 , output = 13

### Methods using C++

1 - **Using recrusion**

```
  #include <iostream>

  #include<cmath>
 
  using namespace std;
   int fib(int m)
   {
     if (m<2)
         return m;
     else
         return fib(m-1)+fib(m-2);
    }
 
    int main() {
      int n;
      cin>>n;
      cout<<fib(n);
 }
 ```
 
 > Time complexity : Exponential

> Space complexity ;  O(n) if we consider the function call stack size, otherwise O(1).

2 -**Using Dynamic programming** 
```
#include<bits/stdc++.h>
#include <iostream>
#include<cmath>
#include<algorithm>
#include<string>
#include<bits/stdc++.h>
using namespace std;


int main() {
     int n;
     cin>>n;
     int a[1000];
     a[0]=0;
     a[1]=1;
     for(int i=2;i<=n;i++)
     {
         a[i]=a[i-1]+a[i-2];
     }
     cout<<a[n];
 }
```

> Time Complexity : O(n)
> 
> Space Complexity : O(n)
 
 3 - **Space Optimized Method 2**
 ```
 #include<bits/stdc++.h>
#include <iostream>
#include<cmath>
#include<algorithm>
#include<string>
#include<bits/stdc++.h>
using namespace std;


int main() {
     int n;
     cin>>n;
     int x,y ,z;
     x=0;
     y=1;
     if(n<2)
         cout<<n;
     else
     {
         for(int i=2;i<=n;i++)
         {
             z=y+x;
             x=y;
             y=z;

         }

         cout<<y;
     }




 }
```
> Time Complexity : O(n)
> 
> Space Complexity : O(1)
 
 4 - **Using Binet’s formula**
 
 ** formula : ** Fn = {[(√5 + 1)/2] ^ n} / √5 
 
 ```
 #include<bits/stdc++.h>
#include <iostream>
#include<cmath>
#include<algorithm>
#include<string>
#include<bits/stdc++.h>
using namespace std;


int main() {
     int n;
     cin>>n;
     double x;
     x=(sqrt(5)+1)/2;
     cout<<round(pow(x,n)/sqrt(5));

}
```
> Time Complexity: O(logn), this is because calculating phi^n takes logn time
> 
> Space Complexity : O(1)

1 - **
 
