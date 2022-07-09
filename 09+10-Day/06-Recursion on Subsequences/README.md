## Video Notes

![vlcsnap-2022-07-09-11h45m35s877](https://user-images.githubusercontent.com/37560890/178095161-1eb07cf8-0c61-4dd6-b11a-396579329895.png)
![vlcsnap-2022-07-09-11h45m50s702](https://user-images.githubusercontent.com/37560890/178095164-3e0ff8ed-4b9e-40d5-b702-1450a1ea48e8.png)
![vlcsnap-2022-07-09-11h47m30s700](https://user-images.githubusercontent.com/37560890/178095175-b2dcf6a0-7eef-4b9e-9de1-c77a3c6798ba.png)
![vlcsnap-2022-07-09-11h47m41s377](https://user-images.githubusercontent.com/37560890/178095178-54302022-4970-4a5a-88d2-7046536c5ab9.png)
![vlcsnap-2022-07-09-11h48m42s907](https://user-images.githubusercontent.com/37560890/178095179-34b3de5f-c68d-472d-be2e-79c3bc7a2985.png)
![vlcsnap-2022-07-09-11h48m57s412](https://user-images.githubusercontent.com/37560890/178095180-6e4614df-d62f-4bbe-8fe0-cca97dea1b1e.png)
![vlcsnap-2022-07-09-11h50m30s123](https://user-images.githubusercontent.com/37560890/178095183-920040a9-60ab-4b05-8f5e-56dd99f62465.png)
![vlcsnap-2022-07-09-11h50m35s608](https://user-images.githubusercontent.com/37560890/178095185-be294b0d-3ec0-4e9b-ba3c-1c1581c2d36b.png)
![vlcsnap-2022-07-09-11h53m58s172](https://user-images.githubusercontent.com/37560890/178095186-06496577-5949-4bc7-9cb7-0d97b45886d7.png)
![vlcsnap-2022-07-09-11h54m09s292](https://user-images.githubusercontent.com/37560890/178095188-fd821536-3f09-4bbe-8225-f685b8faa372.png)
![vlcsnap-2022-07-09-11h54m27s807](https://user-images.githubusercontent.com/37560890/178095190-462f50c4-8e12-4f79-b9e1-5aa06ceae21e.png)
![vlcsnap-2022-07-09-11h54m40s978](https://user-images.githubusercontent.com/37560890/178095193-36581df9-46f7-489a-ab8e-ae7e73c63d17.png)
![vlcsnap-2022-07-09-11h54m57s687](https://user-images.githubusercontent.com/37560890/178095195-a5024d03-5c44-4338-9267-f7ab2d48aa9e.png)
![vlcsnap-2022-07-09-11h55m53s871](https://user-images.githubusercontent.com/37560890/178095196-90bcf20e-b401-4c61-81f8-deb06bd931a5.png)
![vlcsnap-2022-07-09-11h56m00s148](https://user-images.githubusercontent.com/37560890/178095202-a17a2c1f-0116-4c6e-948d-6aa23d9a81c7.png)
![vlcsnap-2022-07-09-11h56m35s647](https://user-images.githubusercontent.com/37560890/178095207-55b6a9fd-ac3a-4913-9857-0686cbe3b26d.png)
![vlcsnap-2022-07-09-11h58m34s007](https://user-images.githubusercontent.com/37560890/178095208-0eefcd2c-9e73-40fc-87a3-1651999cb352.png)
![vlcsnap-2022-07-09-11h58m53s772](https://user-images.githubusercontent.com/37560890/178095211-f9d45183-f02b-4551-b9ba-9458b104f299.png)
![vlcsnap-2022-07-09-11h59m01s065](https://user-images.githubusercontent.com/37560890/178095212-575267fb-1585-4106-95e2-8a5c27969363.png)
![vlcsnap-2022-07-09-11h59m13s622](https://user-images.githubusercontent.com/37560890/178095218-96912c86-b780-4ad0-b45d-acff2e4f601a.png)
![vlcsnap-2022-07-09-11h59m53s122](https://user-images.githubusercontent.com/37560890/178095229-26a382cb-5beb-407e-b16b-a74fe9c5b23d.png)
![vlcsnap-2022-07-09-12h00m01s287](https://user-images.githubusercontent.com/37560890/178095231-831e064c-4a12-4e61-9e99-32e22d9e414b.png)
![vlcsnap-2022-07-09-12h00m06s103](https://user-images.githubusercontent.com/37560890/178095239-aa4bba81-5457-4e96-a9ed-365110119eb6.png)
![vlcsnap-2022-07-09-12h17m06s700](https://user-images.githubusercontent.com/37560890/178095244-5cf4c9cb-f95d-46d5-a2fe-70bbb642b9ac.png)
![vlcsnap-2022-07-09-12h18m53s220](https://user-images.githubusercontent.com/37560890/178095246-a2e036cf-ae19-4feb-a47d-3aaafa0c5f2d.png)
![vlcsnap-2022-07-09-12h18m58s582](https://user-images.githubusercontent.com/37560890/178095249-a7bbff54-ef95-4aa5-979e-bd32d3b1df77.png)
![image](https://user-images.githubusercontent.com/37560890/178095257-5fabafae-ae03-41bd-93e8-6c54408c5b4c.png)

```cpp

Tc: O(2^n)
Sc: O(n)

#include<vector>
#include <iostream>
using namespace std;


// Function for recursion calls
void sub(int i,vector<int> &ds, int arr[],int n)
{
    // If the i is equal to n then print the o/p array
    if(i==n)
    {
        for(auto it: ds) 
        {
            cout<<it<<" ";
        }
        cout<<endl;
        return ;
    }
    
    // Take or pick the particular index into subsequence
    // Add the ele into the array  
    if(i==0) cout<<"{}";
    
    // Take case
    sub(i+1,ds,arr,n);
    ds.push_back(arr[i]);

    // Not take case
    sub(i+1,ds,arr,n);
    
    // Remove case 
    ds.pop_back();
    
    
}
int main()
{
   int a[] = {3,1,2};
   int n= 3;
   vector<int> ds;
   sub(0,ds,a,n);
    
    return 0;
}

```
