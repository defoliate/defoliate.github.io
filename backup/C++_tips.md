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
**delete->deallocates single, delete[] ->[free array](https://stackoverflow.com/questions/2425728/delete-vs-delete-operators-in-c)**

=======

refeer->[memory](https://classes.engr.oregonstate.edu/eecs/winter2020/cs161-020/calendar/lecture15-W20.pdf)

**Reference VS Pointers**

referece->*alians* to some variables,e.g. int& r = s;//has to give value meantime.
pointers->*address* of some variables, e.g. int* p = &s;//Can be declared, then initialized later

**stack->static, compile time _VS_ heap->dynamic, run time**
```C++
//Static
int *i = NULL, j=2; 
i=&j;

//Dynamic, use keyword new
int *i = new int; //Segmentation Fault if didn't set
*i=2;
//no delete->memory leak, not set to NULL:dangling pointers
delete i;
i = NULL; // set the pointer back to NULL return 0;
```
=======
**name of array holds the address of the first item(0th)**
```C++
int grades[5] = {90, 80, 85, 95, 100};
  cout << "grades: "     << grades << endl;//same as &grades[0]
  cout << "grades[0]: "  << grades[0] << endl;//same as *grades
  cout << "&grades[0]: " << &grades[0] << endl;
  cout << "*grades: "    << *grades << endl;
```
=======

