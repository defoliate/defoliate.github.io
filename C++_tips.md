## C++ tip list

**build in data types**

int, float, double, short, long, char, bool

*Note:  <span style="color: red;">std::string</span> wasn't since it's defined by [standard libray](https://stackoverflow.com/questions/5388685/c-is-string-a-built-in-data-type/5388729)*

**return nothing**

function main() should return a int in C++, or could be [without return](https://stackoverflow.com/questions/30354097/how-to-printf-a-memory-address-in-c/30354164) 
```C++
int main(void) 
{//return 0;
}
```
**let pionter to NULL is a good habit**
```C++
int* p = NULL;
```
**Static and Dynamic memory**
```C++
int main(void){
// Static: copy address
int *k =NULL,j=2;
k=&j;
cout<<*k<<endl;
// Dynamic: "create" the address space->new
int *i= new int;
*i = 2;
cout<<*i;
delete i;//delete the memory the pointer points to, not the pointer itself
}
```
**Array: ordered arrangement of similar items**

**C-style string->char end with null**
```C
//code are equal below
char name[5] = {'L', 'u', 'c', 'y', '\0'};
char name[5] = {"Lucy"}; 
```
