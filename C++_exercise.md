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
