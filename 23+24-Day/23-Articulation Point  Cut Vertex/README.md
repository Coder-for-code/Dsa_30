## Video Notes

![vlcsnap-2022-06-11-12h27m59s491](https://user-images.githubusercontent.com/37560890/173185741-0a5491d7-a725-4b6b-bedb-62e6702c934d.png)
![vlcsnap-2022-06-11-12h40m33s713](https://user-images.githubusercontent.com/37560890/173185744-adf5b97f-ca96-443b-ad91-2f616b4b2e11.png)
![vlcsnap-2022-06-11-12h41m17s146](https://user-images.githubusercontent.com/37560890/173185745-04004e9f-87b1-488b-9fc4-0e9aa4ef3bc0.png)
![vlcsnap-2022-06-11-12h42m49s544](https://user-images.githubusercontent.com/37560890/173185746-6dc956af-b8d5-4776-a389-862db8e10246.png)
![vlcsnap-2022-06-11-12h43m49s941](https://user-images.githubusercontent.com/37560890/173185748-bf4b9a15-7c12-4e77-b439-5fabc063781e.png)
![vlcsnap-2022-06-11-12h44m20s748](https://user-images.githubusercontent.com/37560890/173185749-9f11643b-1981-4069-aea4-7f7f4dded3ae.png)
![vlcsnap-2022-06-11-12h45m48s921](https://user-images.githubusercontent.com/37560890/173185750-0e1acadc-2854-4dcc-9251-25f88b905900.png)
![vlcsnap-2022-06-11-12h47m25s394](https://user-images.githubusercontent.com/37560890/173185751-675660a2-abc3-4170-bcda-f951a2643b3a.png)
![vlcsnap-2022-06-11-12h48m20s862](https://user-images.githubusercontent.com/37560890/173185752-e6e0e55e-7d68-4f32-9f89-7c0385f9ad82.png)
![vlcsnap-2022-06-11-12h49m35s578](https://user-images.githubusercontent.com/37560890/173185754-3d21ca34-a299-4321-a1b6-a3d9f7e4680c.png)
![vlcsnap-2022-06-11-12h50m14s163](https://user-images.githubusercontent.com/37560890/173185755-78becf19-4cfc-46bb-8c13-c66e35f71396.png)
![vlcsnap-2022-06-11-12h50m46s057](https://user-images.githubusercontent.com/37560890/173185756-3e6a7367-a68f-4013-b7d0-c2627675670c.png)
![vlcsnap-2022-06-11-12h52m18s000](https://user-images.githubusercontent.com/37560890/173185758-b5f4b561-3c72-4618-84bd-fb9cbe6d568b.png)
![vlcsnap-2022-06-11-12h53m09s587](https://user-images.githubusercontent.com/37560890/173185759-9aa60928-54a3-4ed2-bfdb-4a35ea37b652.png)
![vlcsnap-2022-06-11-12h53m14s879](https://user-images.githubusercontent.com/37560890/173185760-682f24e1-e388-43fa-b00c-5abe0ea7f950.png)
![vlcsnap-2022-06-11-12h53m42s676](https://user-images.githubusercontent.com/106215989/173185780-4fa1bdcc-ab66-4719-8c7b-f1585c708739.png)
![vlcsnap-2022-06-11-12h53m59s482](https://user-images.githubusercontent.com/106215989/173185782-1623cecc-daa6-4296-8f6f-573539e8e224.png)
![vlcsnap-2022-06-11-12h54m50s920](https://user-images.githubusercontent.com/106215989/173185783-73dddfac-751b-47be-a3d5-94ec2e40cbac.png)
![vlcsnap-2022-06-11-12h55m05s809](https://user-images.githubusercontent.com/106215989/173185784-9610ec11-24b9-4569-b1da-b26e2bf54961.png)
![vlcsnap-2022-06-11-16h30m53s503](https://user-images.githubusercontent.com/106215989/173185785-d790f051-9da8-45d2-813c-48e27848ddea.png)
![vlcsnap-2022-06-11-16h31m33s984](https://user-images.githubusercontent.com/106215989/173185786-d525b7e9-b4bb-4a7e-9f2f-f9941e38e155.png)
![vlcsnap-2022-06-11-16h32m08s974](https://user-images.githubusercontent.com/106215989/173185787-0628d7b1-7c8a-4115-9be5-e776e112679f.png)

```cpp

#include <iostream>
using namespace std;



void dfs(int node,int parent,vector<int>&visited,vector<int>&time_to_insert,vector<int>&lowest_time,
int &timer,vector<int> adj[],vector<int> &is_articulation)
{
    // Make the first node as a visited
    visited[node]=1;
    
    // Assign a timer to each and every node
    time_to_insert[node]=lowest_time[node]=timer++;
    
    // Assign the child var
    int child=0;
    
    // Travel and explore it's nbrs
    for(auto it: adj[node])
    {
        // If it's a backward then don't do anything
        if(it==parent) continue;
        
        // If not visited then call dfs
        if(!visited[it])
        {
            // This call will reach to the end 
            dfs(it,node,visited,time_to_insert,lowest_time,timer,adj,is_articulation);
            
            // After end backtracking the call
            // After coming back we always update the lowest_time
            lowest_time[node]= min(lowest_time[node],lowest_time[it]);
            
            // Now check can it be an edge bridge
            if(lowest_time[it]>=time_to_insert[node] and parent!= -1)
            {
                is_articulation[node]=1;
            }
        }
        
        // If the node is previously visited
        // So just compare time and update the lowest_time
        else
        {
            lowest_time[node]= min(lowest_time[node],time_to_insert[it]);
        }
        
    }
    
    // Edge case checking
    if(parent == -1 and child>1)
    {
        is_articulation[node]=1;
    }
    
}


int main()
{
    // n= No of nodes and m = No of edges
    int n,m;
    cin>>n>>m;
    
    // Adj list declaration
    std::vector<int> adj[n] ;
    
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
    vector<int> is_articulation(n,0);
    
    // Timer var
    int timer= 0;
    
    // For every component make a dfs call
    for(int i=0;i<n;i++)
    {
        if(!visited[i])
        {
            dfs(i,-1,visited,time_to_insert,lowest_time,timer,adj,is_articulation);
        }
    }
    
    
    for(int i=0;i<n;i++)
    {
        if(is_articulation[i]==1) cout<<i<<endl;
    }
    
    return 0;
}


```
