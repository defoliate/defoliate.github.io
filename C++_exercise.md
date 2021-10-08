## C++ exercises

**pass by reference**
```C++
//get the address of the third value, not necessary same name(s,a)
void comput_sum(int a, int b, int& s){
    //operate the value in the "box"
    s = a + b;
}

//in C++, must return a int
int main(){
    int x = 2, y = 3, a =0;
    //pass the reference<-decided by the receive func comput_sum(int,int,int&)
    comput_sum(x,y,a);
    cout<<a<<endl;
    //0->successful to the OS,1->some error
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
    comput_sum(x,y,&sum);//pass the address,but dereference the address to value
    cout<<sum<<endl;
    return 0;
}
