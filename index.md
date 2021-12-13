# Report about Const and & in C++
<h3>Const usages: </h3>

### 1. Const keyword.
    allows us to specify the modification of a variable.

  e.g: 

  ```

  const int pi = 3.14;

  ```

  or we can write it like

  ```

  int const pi = 3.14;

  ```

  <hr><br>

  ### 2. Const pointers.
  there are two ways of declaring a const pointer:

  - 1st way prevents you from changing what is pointed to.
  e.g: 

  ```
  const int *p;
  ```

  - 2nd way prevents you from changing the data pointed to.
  e.g:

```
 int x;
int* const p = &x;
```

<hr><br>

### 3. Const Functions
They're used in case we don't want to change the object <b>briefly</b> it's used when we use const objects and Const functions can always be called unlike non-const ones which they can be used only with non-const object</li>
e.g:

```
void Fun(int day_hours) const
 {//Function's arguments }
 ```
 
<hr><br>

### 4. Const overloading.
It's used when we have 2 functions with the same name and the same number and type of parameters but one of these methods is const and the other one is not const.
e.g:

```
#include<iostream>
using namespace std;
class a {
    public:
void fun() const
{cout<<"Const function"<< endl;
}
void fun(){
    cout<< "Non-const function"<< endl;
    }
};
int main(){
    const a obj;
    obj.fun();
    a obj2;
    obj2.fun();
    return 0;
}
```

The Output:

```
Const function
Non-const function
```

<hr>

### 5. Const Iterators.
What are the iterators? they're objects similar to pointers but used to iterate over a sequence and manipulate it's elements
they can be const which they can only iterate through (points to) the data elements and can't modify them but we can update it's value by using ++ or -- operators.
e.g:

```
#include<iostream>
#include<iterator>
#include<vector>
using namespace std;
void regIt(vector<int>& v)
{
    // Declare a regular iterator
    // to a vector
    vector<int>::iterator i;
  
    // Printing the elements of the
    // vector v using regular iterator
    for (i = v.begin(); i < v.end(); i++) {
  
        // Update elements of vector
        *i += 1;
        cout << *i << " ";
    }
}
  
void constIt(vector<int>& v1)
{
    // Declare a const_itearor
    // to a vector
    vector<int>::const_iterator c;
  
    // Printing the elements of the
    // vector v1 using regular iterator
    for (c = v1.begin(); c < v1.end(); c++) {
  
        // Below line will throw an error
        // as we are trying to modify the
        // element to which const_iterator
        // is pointing
  
        //*c += 1; will generate an error as we cannot modify the pointed value
  
        cout << *ci << " ";
    }
}
int main()
{
    // Declaring vectors
    vector<int> v = { 1, 2, 3 };
    vector<int> v1 = { 5, 6, 0 };

    regIt(v);
  
    cout << endl;
    constIt(v1);
    return 0;
}
```

Output:

```
2 3 4
5 6 0
```

<hr>

### 6. Const Cast
When we want to a const variable to function which isn't const but we are pretty sure that function will not change that variable we then can use const_cast so it will make us able to use that non-const fuction with const variables
endeed const_cast is like normal casting the only difference here is that we are casting the constantness but not changing the type

```
// a bad version of strlen that doesn't declare its argument const
int bad_strlen (char *x)
{
        strlen( x );
}
 
// note that the extra const is actually implicit in this declaration since
// string literals are constant
const char *x = "abc";
 
// cast away const-ness for our strlen function 
bad_strlen( const_cast<char *>(x) );
```

<hr>

### 7. Const class parameters
They're like any parameters in the class but the only difference is that there initialization is done in the constructor.
e.g:

```
class Human {
    const int age;
    public:
    Human (int a) age(a){}
}
```

<hr>

## & sympol uses

### 1. Bitwise operator
It compares each bit of the 1st operand to the 2nd operand if the bits are 1 and 1 then the o/p is 1 otherwise is 0.
e.g: 

```
#include<iostream>
using namespace std;
int main(){
    unsigned short a = 0x1111;
    unsigned short b = 0xAAAA;
    cout<< hex <<(a&b)<< endl;
}
```

The Output:

```
0
```

### 2. Adress of operator
It is used to return the address of the variable and it's value is stored in a pointer.
e.g:

```
<br><hr>
#include<iostream>
using namespace std;
int main(){
    int a = 5; 
    int* ptr = &a; 
cout<< "The value of a is "<< a << endl;
cout<< "The value of the pointer ptr is " << ptr << endl;
}

```

The Output:

```
The value of a is 5
The value of the pointer ptr is 0xbfca4345
```

<br><hr>

### 3.  Logical AND operator
such using it in different condition in c++ 
e.g:

```
if(a> 1 && a< 2)
```

<br><hr>
