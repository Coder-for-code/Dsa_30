## 22-[Bridges in a Graph Cut Edge](https://www.geeksforgeeks.org/bridge-in-a-graph/#:~:text=An%20edge%20in%20an%20undirected,increases%20number%20of%20disconnected%20components.)

## Video Notes

![vlcsnap-2022-06-11-11h03m00s401](https://user-images.githubusercontent.com/37560890/173176543-38a397bb-00f6-4953-9fcc-a5ea5c0e7217.png)
![vlcsnap-2022-06-11-11h03m22s624](https://user-images.githubusercontent.com/37560890/173176544-30a3a44d-2dcb-4a46-ae3f-7ae41118e40f.png)
![vlcsnap-2022-06-11-11h03m49s094](https://user-images.githubusercontent.com/37560890/173176545-ed67763d-0571-424a-affd-19a04c4b95dd.png)
![vlcsnap-2022-06-11-11h23m02s787](https://user-images.githubusercontent.com/37560890/173176547-29edaf5f-1925-49b2-9f58-66e0d2b5c55f.png)
![vlcsnap-2022-06-11-11h27m42s601](https://user-images.githubusercontent.com/37560890/173176549-eea822b5-3296-42a1-9eaf-fdc12bc5c110.png)
![vlcsnap-2022-06-11-11h28m04s418](https://user-images.githubusercontent.com/37560890/173176550-ab4b2e7e-c972-41b7-9576-15ac29905611.png)
![vlcsnap-2022-06-11-11h28m30s787](https://user-images.githubusercontent.com/37560890/173176551-6e5d5acd-f9d6-486d-8aad-4d0242a9adb5.png)
![vlcsnap-2022-06-11-11h28m56s486](https://user-images.githubusercontent.com/37560890/173176552-649dd814-804e-4bb5-8b01-bb5371d80e27.png)
![vlcsnap-2022-06-11-11h30m10s861](https://user-images.githubusercontent.com/37560890/173176553-ff1bcd93-5d6d-4b46-a274-a2dea80b9620.png)
![vlcsnap-2022-06-11-11h30m13s681](https://user-images.githubusercontent.com/37560890/173176556-a6586d62-b606-4496-9955-9386cb041d9b.png)
![vlcsnap-2022-06-11-11h31m34s981](https://user-images.githubusercontent.com/37560890/173176558-c3cc52e6-df93-4a23-9287-cca0de671711.png)
![vlcsnap-2022-06-11-11h32m14s936](https://user-images.githubusercontent.com/37560890/173176559-99bc1940-6c4e-4ac4-829e-5fcc460e5518.png)
![vlcsnap-2022-06-11-11h33m54s857](https://user-images.githubusercontent.com/37560890/173176561-333897a9-9ab4-4b4f-bc6d-8d79485853cf.png)
![vlcsnap-2022-06-11-11h36m09s249](https://user-images.githubusercontent.com/37560890/173176563-972b59a7-1f3e-4e46-ada2-68673e1ee52c.png)
![vlcsnap-2022-06-11-11h36m26s358](https://user-images.githubusercontent.com/37560890/173176564-6b4a253c-be84-43e0-962e-42fea913de33.png)
![vlcsnap-2022-06-11-11h37m35s342](https://user-images.githubusercontent.com/37560890/173176565-13a581c9-6b64-4d3d-898d-6f7518e46fdb.png)
![vlcsnap-2022-06-11-11h38m13s472](https://user-images.githubusercontent.com/37560890/173176567-74d490cb-2b6f-45cf-b059-f120ba961787.png)
![vlcsnap-2022-06-11-11h39m02s113](https://user-images.githubusercontent.com/37560890/173176568-7880ff2a-229a-4b13-9ec8-95b197bc1cce.png)
![vlcsnap-2022-06-11-11h39m44s336](https://user-images.githubusercontent.com/37560890/173176571-4a44fba6-419e-417e-816d-be9524bac163.png)
![vlcsnap-2022-06-11-11h40m23s533](https://user-images.githubusercontent.com/37560890/173176573-b77ac069-4374-4c52-bc93-08df931e7484.png)
![vlcsnap-2022-06-11-11h40m30s948](https://user-images.githubusercontent.com/37560890/173176574-f9acda95-c0c9-46b4-baa3-95943d1b9855.png)
![vlcsnap-2022-06-11-11h45m46s474](https://user-images.githubusercontent.com/37560890/173176575-1d23db6f-9801-47e5-a11d-ac57a7e7ea7f.png)
![vlcsnap-2022-06-11-12h07m16s117](https://user-images.githubusercontent.com/37560890/173176577-a50e0bdd-a75f-475c-af70-2e34cfe219d4.png)


```cpp


#include <iostream>
using namespace std;



void dfs(int node,int parent,vector<int>&visited,vector<int>&time_to_insert,vector<int>&lowest_time,
int &timer,vector<int> adj[])
{
    // Make the first node as a visited
    visited[node]=1;
    
    // Assign a timer to each and every node
    time_to_insert[node]=lowest_time[node]=timer++;
    
    // Travel and explore it's nbrs
    for(auto it: adj[node])
    {
        // If it's a backward then don't do anything
        if(it==parent) continue;
        
        // If not visited then call dfs
        if(!visited[i])
        {
            // This call will reach to the end 
            dfs(it,node,visited,time_to_insert,lowest_time,timer,adj);
            
            // After end backtracking the call
            // After coming back we always update the lowest_time
            lowest_time[node]= min(lowest_time[node],lowest_time[it]);
            
            // Now check can it be an edge bridge
            if(lowest_time[it]>time_to_insert[node])
            {
                cout<<node<<" "<<it<<endl;
                
            }
        }
        
        // If the node is previously visited
        // So just compare time and update the lowest_time
        else
        {
            lowest_time[node]= min(lowest_time[node],time_to_insert[it]);
        }
        
    }
    
}


int main()
{
    // n= No of nodes and m = No of edges
    int n,m;
    cin>>n>>m;
    
    // Adj list declaration
    std::vector<int> adj[] ;
    
    // Take the input as a graph
    for(int i=0;i<m;i++)
    {
        // Add the edges
        int u,v;
        cin>>u>>v;
        
        // Since it's a undirected add the bidirectional edge
        adj[u].push_back(v);
        adj[v].push_back(u);
    }
    
    // Make the 3 array's
    vector<int> time_to_insert(n,-1);
    vector<int> lowest_time(n,-1);
    vector<int> visited(n,0);
    
    // Timer var
    int timer= 0;
    
    // For every component make a dfs call
    for(int i=0;i<n;i++)
    {
        if(!visited[i])
        {
            dfs(i,-1,visited,time_to_insert,lowest_time,timer,adj);
        }
    }
    
    return 0;
}

```
