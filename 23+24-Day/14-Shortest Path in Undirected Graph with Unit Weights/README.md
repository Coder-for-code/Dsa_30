## Video Notes

![vlcsnap-2022-06-09-12h47m35s211](https://user-images.githubusercontent.com/37560890/173049562-a01cc4ba-2969-428c-a9a8-a943944d784f.png)
![vlcsnap-2022-06-09-12h50m05s341](https://user-images.githubusercontent.com/37560890/173049569-35cafc37-47c2-4324-a7b4-8412a27704e6.png)
![vlcsnap-2022-06-09-13h02m45s445](https://user-images.githubusercontent.com/37560890/173049574-36d4ec90-05d6-4763-a537-1cb0b8440c52.png)
![vlcsnap-2022-06-09-13h04m48s294](https://user-images.githubusercontent.com/37560890/173049576-d12a4e4a-52ec-4c95-9668-306754875bba.png)
![vlcsnap-2022-06-09-13h06m58s950](https://user-images.githubusercontent.com/37560890/173049579-3293febd-b18d-43c7-a43e-240ce17ef940.png)
![vlcsnap-2022-06-09-13h51m33s238](https://user-images.githubusercontent.com/37560890/173049583-c44de76f-25d8-43f3-b98d-ead7a1fc98e1.png)
![vlcsnap-2022-06-10-16h06m09s861](https://user-images.githubusercontent.com/37560890/173049586-f3fefa63-9a3c-49cb-b72e-f3ded6f9dcda.png)
![vlcsnap-2022-06-10-16h07m06s418](https://user-images.githubusercontent.com/37560890/173049589-3b9b39b3-f291-4c07-87a8-23e39405cf88.png)
![vlcsnap-2022-06-10-16h07m19s815](https://user-images.githubusercontent.com/37560890/173049590-8763e268-9baf-4fe7-977a-ea5972f24388.png)


```cpp

#include <iostream>
using namespace std;

void bfs(std::vector<int> adj[], int n , int src)
{
    // Create a distance array
    int dist[n];
    
    // Initialize the dist array as an infinity
    for(int i=0;i<n;i++)
    {
        dist[i] = INT_MAX;
    }
    
    // Create a queue
    queue<int> q;
    
    // Mark the src distance as 0
    dist[src] =0;
    
    // Iterate till queue not empty
    while(!q.empty())
    {
        int node= q.front();
        q.pop();
        
        // Explore it's nbrs
        for(auto nbrs: adj[node])
        {
            // Update the distance's accordingly
            if(dist[node]+1 < dist[nbrs])
            {
                dist[nbrs]= dist[node] + 1;
                q.push(nbrs);
            }
        }
    }
    
    // Print the distance array
    for(auto i=0;i<n;i++)
    {
        cout<<dist[i]<<" ";
    }
    
    
}

```
