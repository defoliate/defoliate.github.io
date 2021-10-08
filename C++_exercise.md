## C++ exercises

**pass by reference**
```C++
// get the address of the third value, not necessary same name(s,a)
void comput_sum(int a, int b, int& s){
    //operate the value in the "box"
    s = a + b;
}

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
```

**pass by Reference and Pointer difference**
```C++
int main(void){
// Reference: just an alias of some variable(permanent),
// must be declared and initialize same time.
int s=10;
//r is the alias of s->have been initialized after declared
int& r=s;
s = 101;
//can be pass
int t=r;
//int r= 11; error->can't be alias to others
cout<<"Reference sample:\n"<<r<<","<<s<<","<<t<<endl;

// Pointer:stores address of some variable,changa content of address anytime
// can be declared first and initialized later.
int* p;//not initialized
p= &s;//p is the pointer,not *p->the value of the pointer
cout<<"Pointer sample:\n"<<*p;
}
```
