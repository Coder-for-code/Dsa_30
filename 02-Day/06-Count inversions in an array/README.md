6. https://www.codingninjas.com/codestudio/problems/count-inversions_615

![6](https://user-images.githubusercontent.com/37560890/166860616-dc31dac7-9b67-4d62-8d26-5e715090eb0f.jpg)

Solution 1: Modified merge sort 

```cpp
#include<bits/stdc++.h>
using namespace std;

int merge(int arr[],int temp[],int left,int mid,int right)
{
    int inv_count=0;
    int i = left;
    int j = mid;
    int k = left;
    while((i <= mid-1) && (j <= right)){
        if(arr[i] <= arr[j]){
            temp[k++] = arr[i++];
        }
        else
        {
            temp[k++] = arr[j++];
            inv_count = inv_count + (mid - i);
        }
    }

    while(i <= mid - 1)
        temp[k++] = arr[i++];

    while(j <= right)
        temp[k++] = arr[j++];

    for(i = left ; i <= right ; i++)
        arr[i] = temp[i];
    
    return inv_count;
}

int merge_Sort(int arr[],int temp[],int left,int right)
{
    int mid,inv_count = 0;
    if(right > left)
    {
        mid = (left + right)/2;

        inv_count += merge_Sort(arr,temp,left,mid);
        inv_count += merge_Sort(arr,temp,mid+1,right);

        inv_count += merge(arr,temp,left,mid+1,right);
    }
    return inv_count;
}

int main()
{
    int arr[]={5,3,2,1,4};
    int n=5;
    int temp[n];
    int ans = merge_Sort(arr,temp,0,n-1);
    cout<<"The total inversions are "<<ans<<endl; 


    return 0;
}
```
