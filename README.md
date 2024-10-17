# EXPERIMENT 20
# AIM:
To study and implement Sorting Algorithm

1.Selection sort  
2.Insertion sort  
3.Bubble sort

# SOFTWARE USED 
Visual Studio Code 
# THEORY:
In C++, sorting refers to the process of arranging elements in a specific order, typically in ascending or descending order. Sorting algorithms can be applied to arrays, vectors, or other containers to reorder the elements based on their values.

1. Selection Sort:
Selection Sort works by repeatedly finding the minimum element from the unsorted part of the array and swapping it with the first unsorted element.

a) Time Complexity: O(n²) for all cases.

b) Space Complexity: O(1) (in-place sorting).


2. Insertion Sort:
Insertion Sort works by building a sorted array one element at a time. It picks each element and inserts it into its correct position within the already sorted part of the array.

a) Time Complexity: O(n²) in the worst case; O(n) in the best case (already sorted).

b) Space Complexity: O(1) (in-place sorting).

3. Bubble Sort:
Bubble Sort repeatedly swaps adjacent elements if they are in the wrong order. The largest element "bubbles up" to its correct position after each pass.

a) Time Complexity: O(n²) in the worst case.

b) Space Complexity: O(1) (in-place sorting).


1.Selection sort:
```
#include<iostream>
using namespace std;
void swap(int *a,int *b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
void s_sort(int *a, int elements){
    int n=0;
    int *b;
    while (n!=elements){
        b=a+1;
        for (int i=0; i< (elements-1)-n;i++){
            if(*a>*b){
                swap(a,b);
            }
             b++;
        }
        n++;
        a++;
    }   
}
int main(){
    int no_el;
    cout <<"How many elements in your array ?"<<endl;
    cin>>no_el;
    int arr[no_el];
    cout<<"Enter "<<no_el<<" Elements:"<<endl;
    for (int i=0;i<no_el;i++){
        cin>>arr[i];
    }
    cout<<"Sorted Array:";
    s_sort(&arr[0],no_el);
    for (int i=0; i<no_el;i++){
        cout<<arr[i]<<" ";
    }
    return 0;
}
```
OUTPUT:

![image](https://github.com/user-attachments/assets/764ce06d-9ae8-4c7b-a1f3-f1ef79737229)


2.Insertion sort:
```
#include<iostream>
using namespace std;
void insertionSort(int arr[], int n ){
    for (int i = 1; i < n; i++){
        int key=arr[i];
        int j=i-1;
        while (j>=0 && arr[j]>key){
            arr[j+1]=arr[j];
            j--;
        }
        arr[j+1]=key;
    }
}
int main(){
    int arr[]={64, 25, 12, 22, 11};
    int n= sizeof(arr)/ sizeof(arr[0]);
    cout<< "Original array: ";
    for (int i=0;i<n;i++){
        cout << arr[i] << " ";
    }
    insertionSort (arr,n);
    cout<< "\n Sorted array: ";
    for (int i = 0; i < n; i++){
        cout <<arr[i] << " ";
    }
    return 0;
}
```
OUTPUT:

![image](https://github.com/user-attachments/assets/9d7d91cc-3448-4b4d-9a30-79b30d46aabe)


3.Bubble sort:
```
#include<iostream>
using namespace std;
void swap(int *a,int *b){
    int temp;
    temp=*a;
    *a=*b;
    *b=temp;
}
int main(){
    int elements;
    cout<<"How many elements in the array?:";
    cin>>elements ;
    int array[elements];
    cout<<" Enter elements: ";
    for (int i = 0; i < elements ; i++){
        cin>>array[i];
    }
    for (int i = 0; i < elements; i++){
        cout<<array[i]<<" ";
    }
    int n=0;
    while(n!=elements){
        for(int i = 0 ; i < elements - n ; i++){
            if (array[i] > array[i+1]){
                swap(&array[i], &array[i+1]);
            }
        }
        n++;
    }
    cout << "\nSorted array is: "<< endl;
    for(int i = 0; i < elements; i++){
        cout << array[i]<<" ";
    }
    return 0;
}
```
OUTPUT:

![image](https://github.com/user-attachments/assets/a746bdd2-b349-4ff2-9468-8585a2b30213)


# CONCLUSION:
These algorithms are primarily useful for educational purposes, and while they work well on small datasets, more advanced sorting algorithms such as Quick Sort, Merge Sort, or Heap Sort are generally preferred for large datasets due to their better performance.
