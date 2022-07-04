# 06-House Robber[]

### Video Notes

![vlcsnap-2022-07-03-18h08m56s227](https://user-images.githubusercontent.com/37560890/177069342-ce7655a5-f270-4873-94ad-76b8abdd34fb.png)
![vlcsnap-2022-07-03-18h12m59s280](https://user-images.githubusercontent.com/37560890/177069344-5fda7439-705d-4ee5-bf12-41d61cdd301d.png)
![vlcsnap-2022-07-03-18h13m23s520](https://user-images.githubusercontent.com/37560890/177069347-584c8cc6-4493-4c55-ac35-194ba3a09cf1.png)
![vlcsnap-2022-07-03-18h13m41s846](https://user-images.githubusercontent.com/37560890/177069350-c04795da-18ee-4fb7-9170-1b2dc7f93467.png)
![vlcsnap-2022-07-04-07h29m59s188](https://user-images.githubusercontent.com/37560890/177069352-ff8234af-0ec0-48e2-9364-12c9b8c65c0e.png)
![vlcsnap-2022-07-04-07h30m24s341](https://user-images.githubusercontent.com/37560890/177069354-049cf5f1-2e13-4e82-9208-60c2e3f1b63d.png)
![vlcsnap-2022-07-04-07h31m32s576](https://user-images.githubusercontent.com/37560890/177069356-311451a8-3a71-4b68-899b-3090d2385d22.png)
![vlcsnap-2022-07-04-07h32m11s329](https://user-images.githubusercontent.com/37560890/177069358-abdcce91-b45d-4fc9-97a2-e0994087a2ce.png)
![vlcsnap-2022-07-04-07h32m33s196](https://user-images.githubusercontent.com/37560890/177069359-bbe18e05-0c06-4f41-a2c4-5653dd741b8d.png)
![vlcsnap-2022-07-04-07h33m05s456](https://user-images.githubusercontent.com/37560890/177069360-b6bd7799-d0f5-4cd5-9f7e-326d938af668.png)
![vlcsnap-2022-07-04-07h33m16s074](https://user-images.githubusercontent.com/37560890/177069362-ad14b36c-7553-4ebf-a05a-532155f7a18e.png)
![vlcsnap-2022-07-04-07h34m12s321](https://user-images.githubusercontent.com/37560890/177069365-d0cff3d5-f499-4257-a54f-4d56a66c3fd3.png)
![vlcsnap-2022-07-04-07h35m28s531](https://user-images.githubusercontent.com/37560890/177069367-edbf6532-6c65-426c-a069-7e867ed6e1d6.png)
![vlcsnap-2022-07-04-07h35m53s726](https://user-images.githubusercontent.com/37560890/177069369-86eedbd9-0dc5-4385-a75f-1da0b91d9e2d.png)
![vlcsnap-2022-07-04-07h36m10s401](https://user-images.githubusercontent.com/37560890/177069370-1d44486e-3411-4423-829c-323bcbc93636.png)
![vlcsnap-2022-07-04-07h36m14s258](https://user-images.githubusercontent.com/37560890/177069371-4d956a2c-eb08-4eb5-857b-8a14701d49c2.png)
![vlcsnap-2022-07-04-07h36m18s361](https://user-images.githubusercontent.com/37560890/177069372-30b8b8e9-b639-4f1c-8ff0-0f30832f9d6d.png)

```cpp
Tc: O(n)
Sc: O(1)
#include <bits/stdc++.h>

using namespace std;

long long int solve(vector<int>& arr)
{
    int n = arr.size();
    long long int prev = arr[0];
    long long int prev2 =0;
    
    for(int i=1; i<n; i++)
    {
        long long int pick = arr[i];
        if(i>1)
            pick += prev2;
        int long long nonPick = 0 + prev;
        
        long long int cur_i = max(pick, nonPick);
        prev2 = prev;
        prev= cur_i;
        
    }
    return prev;
}

long long int robStreet(int n, vector<int> &arr)
{
    vector<int> arr1;
    vector<int> arr2;
    
    for(int i=0; i<n; i++)
    {
        
        if(i!=0) arr1.push_back(arr[i]);
        if(i!=n-1) arr2.push_back(arr[i]);
    }
    
    long long int ans1 = solve(arr1);
    long long int ans2 = solve(arr2);
    
    return max(ans1,ans2);
}


int main() {

  vector<int> arr{1,5,1,2,6};
  int n=arr.size();
  cout<<robStreet(n,arr);
}

```
