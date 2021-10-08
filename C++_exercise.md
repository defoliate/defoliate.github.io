## C++ exercises

**pass by reference**
```C++
#include <iostream>
#include <string>
using namespace std;
// pass by reference/address, operate the value since have the address=a box with values
void swapnum(int& i, int& j) {
 int temp = i;
 i = j;
 j = temp;
}
int main() {
 int a = 10, b = 20;
 cout << "A is " << a << " and B is " << b << endl;
 swapnum(a,b);//pass the address of a,b, also means the whole box that contains a,b
 cout << "A is " << a << " and B is " << b << endl;
 return 0;
}
```
**pointer->dereference the address and get the value from it**
```C++
#include <iostream>
using namespace std;

//dereference the value of the address
void comput_sum(int a, int b, int* s){
    //operate the value directly
    *s = a + b;
}

//in C++, must return a int
int main(){
    int x = 2, y = 3, sum =0;
    comput_sum(x,y,&sum);//pass the address
    cout<<sum<<endl;
    //0->successful to the OS,1->some error
    return 0;
}
