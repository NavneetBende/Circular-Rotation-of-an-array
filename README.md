C++ program for the circular rotation of an array by K positions
In this article we’ll be learning about Circular Rotation of an array in C++ which means rotating the elements in the array where one rotation operation moves the last element of the array to the first position and shifts all remaining elements to the right. The example for it is given below.

Circular Rotation of an array in C++
Keypoint
In this section we will learn about basic knowledge which we need to know before coding the above Program. So we must have knowledge of what is an array? 

What is an array?
An array is a data structure, it is collection of similar data elements which is stored at contiguous memory locations in which each data element can be accessed directly by only using its index number.
 
About C++ language:-
C++ Programming Object Oriented Programming C++ is a programming language developed by Bjarne Stroustrup in 1979 at Bell Labs. C++ is a cross-platform language that can be used to create high-performance applications. It is extension of C language. About C++ Programming it is Multi-paradigm Language – C++ supports at least seven different styles of programming. It is General Purpose Language – You can use C++ to develop games, desktop apps, operating systems, and so on and  Speed – Like C programming, the performance of optimized C++ code is exceptional. 
 
 
How to declare an array?
To declare an array in C, a programmer specifies the type of the elements and the number of elements required by an array as follows − This is called a single-dimensional array. The array Size must be an integer constant greater than zero and type can be any valid C data type. For example, to declare a 10-element array called balance of type double, use this statement − Here balance is a variable array which is sufficient to hold up to 10 double numbers
 
Algorithm :
By reversing the array we can circularly rotates the array.
First we will set K to points that element which comes at first position, i.e. K = N-K.
Then , reverse the array from 0 to K-1 position.
After that, again reverse the array from K to N-1 position.
And then finally reverse the entire array.
Doing so we will get the desired circularly rotated array by K position.
 
 
 
Circular Rotations Of Array By K Positions
C++ program for Circular Rotation of an Array :
#include <bits/stdc++.h>
using namespace std;

int main()
{

    int n;    // variable to store the size of the array
    int k;    // variable to store the position for rotation

    cout << "Enter the size of array : ";
    cin >> n;

    cout << "\nEnter the position for rotation : ";
    cin >> k;

    std::vector A(n);    // declaring a vector of size n

    cout << "\nEnter the elements of the array : ";

    for (int i = 0; i < n; i++)
        cin >> A[i];

    k = (n - k) % n;    // set k to the index which comes first

    reverse(A.begin(), A.begin() + k);    //reverse the array from 0 to k position
    reverse(A.begin() + k, A.end());    //reverse the array from k to n-1 position
    reverse(A.begin(), A.end());    //reverse the array from 0 to n-1 position

    cout << "\nArray after rotation: ";

    for (int i = 0; i < n; i++)
        cout << A[i] << " ";

    return 0;

}
Output :
Enter the size of array : 5

Enter the position for rotation : 2

Enter the elements of array : 1 2 3 4 5

Array after rotation : 4 5 1 2 3
