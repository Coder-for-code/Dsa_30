## Video Notes


![vlcsnap-2022-06-10-16h21m00s103](https://user-images.githubusercontent.com/37560890/173066847-cd370cf0-646b-4b13-b36d-70f627b07d26.png)
![vlcsnap-2022-06-10-16h24m58s288](https://user-images.githubusercontent.com/37560890/173066855-ea72b476-2444-4869-a536-13612abfd7e2.png)
![vlcsnap-2022-06-10-16h26m43s595](https://user-images.githubusercontent.com/37560890/173066859-c054a268-9a43-4d61-beba-8649ac224625.png)
![vlcsnap-2022-06-10-16h31m13s807](https://user-images.githubusercontent.com/37560890/173066860-b052bfe5-71b3-4153-b777-dcab0eb280bc.png)
![vlcsnap-2022-06-10-16h40m53s975](https://user-images.githubusercontent.com/37560890/173066861-4d42db12-1f6f-4bc7-b0d3-dd0f8e97f2a3.png)
![vlcsnap-2022-06-10-16h41m43s192](https://user-images.githubusercontent.com/37560890/173066862-2a251bd4-7087-4322-86b5-06257784964d.png)
![vlcsnap-2022-06-10-16h42m52s378](https://user-images.githubusercontent.com/37560890/173066868-4d07423b-da4d-49d0-9c67-f70b12735114.png)
![vlcsnap-2022-06-10-16h44m20s895](https://user-images.githubusercontent.com/37560890/173066871-95472059-64b1-49af-beef-cb11165f2a55.png)
![vlcsnap-2022-06-10-16h44m42s017](https://user-images.githubusercontent.com/37560890/173066877-53066912-8831-43ba-9a15-e52721abdc06.png)
![vlcsnap-2022-06-10-16h45m27s508](https://user-images.githubusercontent.com/37560890/173066881-ceea3da9-be65-446b-a1ac-98f1c909c321.png)
![vlcsnap-2022-06-10-16h47m30s424](https://user-images.githubusercontent.com/37560890/173066884-d1da8f4a-316a-41a2-9018-26c04a6929e9.png)
![vlcsnap-2022-06-10-16h47m48s446](https://user-images.githubusercontent.com/37560890/173066887-8d1b96b6-935e-49b4-8373-57c97aa72034.png)
![vlcsnap-2022-06-10-16h49m00s307](https://user-images.githubusercontent.com/37560890/173066891-a738031e-c8ee-400c-a7e1-21fac60df0b2.png)
![vlcsnap-2022-06-10-18h01m50s481](https://user-images.githubusercontent.com/37560890/173066893-5047f146-f38f-4aa8-8583-b074f2e266c4.png)
![vlcsnap-2022-06-10-18h04m40s150](https://user-images.githubusercontent.com/37560890/173066896-9ac510cf-c5e4-452f-b74b-594132da1861.png)
![vlcsnap-2022-06-10-18h05m10s836](https://user-images.githubusercontent.com/37560890/173066899-9d50e9d9-2c6a-4397-bc3a-26598e973b27.png)



```cpp

#include <iostream>
using namespace std;


// Function to find the topo sort
void find_topo_sort(int node,int visited[],stack<int>&s,vector<pair<int,int>>adj[])
{
    // Make the current node as visited
    visited[node] =1;
    
    // Travel the adjacent nodes
    for(auto it: adj[node])
    {
        if(!visited[it])
        {
            find_topo_sort(it.first,visited,s,adj);
        }
    }
    
    // Finally push the node into the stack
    s.push(node);
}


// Function for finding the shortest_path 
void shortest_path(int src, int n, vector<pair<int,int>> adj[])
{
    // Make a visited array
    int visited[n]= {0};
    
    // Create a stack 
    stack<int> s;
    
    // Function for finding the topo sort
    for(int i=0;i<n;i++)
    {
        if(!visited[i])
        {
            find_topo_sort(i,visited,s,adj);
        }
    }
    
    // Create the distance array
    int dist[n];
    
    // Make all the entries as infinity
    for(int i=0;i<n;i++)
    {
        dist[i]= 1e9;
    }
    
    // Iterate till stack is not empty
    while(!s.empty())
    {
        int node=s.top();
        s.pop()
        
        // Update the distance
        if(dist[node]!=INF)
        {
            for(auto it: adj[node])
            {
                if(dist[node]+it.second < dist[it.first])
                {
                    dist[it.first]= dist[node] + it.second;
                }
            }
        }
        
    }
    
    // Finally print the distance array
    for(int i=0;i<n;i++)
    {
        (dist[i]==1e9) ? cout<<"INF" : cout<<dist[i]<<" "
    }

}

int main()
{
    // N= No of nodes and m = No of edges
    int n,m;
    cin>>n>>m;
    
    // Adjaency matrix
    vector<pair<int,int>> adj[n];
    
    // Input of adj list
    for(int i=0;i<m;i++)
    {
        int u,v,wt;
        cin>>u>>v>>wt;
        adj[u].push_back({v,wt});
    }
    
    // Calling the shortest_path function
    shortest_path(0,n,wt);
    return 0;
}

```
