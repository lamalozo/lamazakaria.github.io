[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=8786081&assignment_repo_type=AssignmentRepo)
# Fibonacci numbers

The sequence of fibonacci numbers may be defined by **recurrence relation** which is equation according to which **nth term** of a sequence of numbers is **equal** to some combination of the previous terms

Fn = Fn-1 + Fn-2

The Fibonacci numbers are the numbers in the following integer sequence.

0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, …….

![Fibonacci_Spiral svg](https://user-images.githubusercontent.com/115074648/194080268-fbf00d7a-6b9e-47cd-8ba1-680a6d5f2f5f.png)

---

## Program of Fibonacci numbers
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

> **Time complexity** : Exponential

> **Space complexity** ;  O(n) if we consider the function call stack size, otherwise O(1).

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

> **Time Complexity** : O(n)
>
> **Space Complexity** : O(n)

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
> **Time Complexity** : O(n)
>
> **Space Complexity** : O(1)

4 - **Using Binet’s formula**

**formula** **:** Fn = {[(√5 + 1)/2] ^ n} / √5

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
> **Time Complexity**: O(logn), this is because calculating phi^n takes logn time
>
> **Space Complexity** : O(1)

5 - **Using power of the matrix {{1, 1}, {1, 0}}**

This is another O(n) that relies on the fact that if we n times multiply the matrix M = {{1,1},{1,0}} to itself (in other words calculate power(M, n)), then we get the (n+1)th Fibonacci number as the element at row and column (0, 0) in the resultant matrix.

```
#include<bits/stdc++.h>
#include <iostream>
#include<cmath>
#include<algorithm>
#include<string>
#include<bits/stdc++.h>
using namespace std;
int r ,w,e,l;
int mulitply(int a[2][2],int b[2][2]) {
   r = a[0][0] * b[0][0] + a[0][1] * b[1][0];
   w = a[0][0] * b[0][1] + a[0][1] * b[1][1];
   e = a[1][0] * b[0][0] + a[1][1] * b[1][0];
   l = a[1][0] * b[0][1] + a[1][1] * b[1][1];
   a[0][0]=r;
   a[0][1]=w;
   a[1][0]=e;
   a[1][1]=l;
}


int main() {
     int n,i;
     cin>>n;
     int x[2][2]=[ (1,1) ,(1,0)];
     int y[2][2]=[ (1,1) ,(1,0)];;
     if (n==0)
         cout<<n;
     else
     {
         for (i=0;i<n-2;i++)
         {
             mulitply(x,y);
         }
         cout<<x[0][0];


     }


}
```
> **Time Complexity** : O(n)
> 
> **Space Complexity** : O(1)
> 

### Comparsion between methods through space and time complexity

| Method                    | Time Complexity     | Space Complexity      |
| -----------------------   | ------------------  | --------------------- |
| Recrusion                 | Exponential         | O(n)                  |
| Dynamic Programming       | O(n)                | O(n)                  |
| Space Optimizied method 2 | O(n)                | O(1)                  |
| Binet's Formula           | O(log(n))           | O(1)                  |
| Power of Matrix           | O(n)                | O(1)                  |



> **Reference**
> 
>  http://en.wikipedia.org/wiki/Fibonacci_number
> 


