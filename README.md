#include <iostream>

using namespace std;

/// The getMax() function returns the maximum
/// integer in the sequence of n integers pointed
/// by p.
int getMax(int *p, int n)
{
int maxInt = 0;
for(int k=0;k<n;k++)
{
    if(*(p+k)>maxInt)
    {

    maxInt=*(p+k);
    }
}
/// TO DO: Add your code here
return maxInt;
}

int main()
{
const int SIZE = 6;
int arr[SIZE] = {3, 5, 9, 2, 6, 8};

/// Use the combinations of [], *, & and/or pointer arithmetic to complete Part 1 and 2
/// in the array.

/// Part 1 - Display the values, i.e. 3, 5, 9, 6, and 8, of the array
cout << "Part 1A" << endl;
for (int i = 0; i < SIZE; i++)
cout << "\t" << arr[i];

cout << endl << endl << "Part 1B" << endl;
/// ADD YOUR CODE HERE
for (int i = 0; i < SIZE; i++)
    cout<<"\t"<< *(arr+i);

/// Part 2 - Display the 6 addresses the elements of the array in two different ways
cout << endl << endl << "Part 2A" << endl;
/// ADD YOUR CODE HERE

for (int i = 0; i < SIZE; i++)

    cout<<"\t"<<arr+i;

cout << endl << endl << "Part 2B" << endl;
/// ADD YOUR CODE HERE
for (int i = 0; i < SIZE; i++)
cout<<"\t"<<&(arr[i]);

/// Part 3

cout << "Part 3 -- Return the max number of the array: " << getMax(arr, SIZE);

return 0;
}
