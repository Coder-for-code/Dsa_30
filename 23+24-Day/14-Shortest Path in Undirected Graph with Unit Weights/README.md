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
