# 10-[Detect cycle in a directed graph](https://practice.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1/#)

<div class="problem-statement">
                <p></p><p><span style="font-size:18px">Given a Directed Graph with <strong>V</strong> vertices (Numbered from <strong>0</strong> to <strong>V-1</strong>) and <strong>E</strong> edges, check whether it contains any cycle or not.</span></p>

![download](https://user-images.githubusercontent.com/37560890/172630598-051e9deb-df39-46fa-aedc-72e564f6bd96.png)

<p><br>
<span style="font-size:18px"><strong>Example 1:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input:</strong></span>

<span style="font-size:18px"><strong>Output:</strong> 1
<strong>Explanation</strong>: 3 -&gt; 3 is a cycle</span></pre>

<p><br>
<span style="font-size:18px"><strong>Example 2:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input:</strong></span>

<span style="font-size:18px"><strong>Output:</strong> 0
<strong>Explanation</strong>: no cycle in the graph</span></pre>

<p><br>
<span style="font-size:18px"><strong>Your task:</strong></span><br>
<span style="font-size:18px">You dont need to read input or print anything. Your task is to complete the function&nbsp;<strong>isCyclic()</strong>&nbsp;which takes the integer V denoting the number of vertices and adjacency list as input parameters and returns a boolean value denoting if the given directed graph contains a cycle or not. </span></p>

<p><br>
<span style="font-size:18px"><strong>Expected Time Complexity:&nbsp;</strong>O(V + E)<br>
<strong>Expected Auxiliary Space:&nbsp;</strong>O(V)</span></p>

<p><br>
<span style="font-size:18px"><strong>Constraints:</strong><br>
1 ≤ V, E ≤ 10<sup>5</sup></span></p>
 <p></p>
 </div>
 
 
 ```cpp
 class Solution 
{
  public:
    
    // Helper function  
    bool checkCycle(int node,vector<int>adj[],int vis[], int dfs_visited[])
    {
        // Mark both visited and dfs visited array to be 1
        vis[node]=1;
        dfs_visited[node]=1;
        
        // Travel to it's nbrs
        for(auto nbrs: adj[node])
        {
            // If nbrs is not visited then call the method
            if(!vis[nbrs])
            {
                if(checkCycle(nbrs,adj,vis,dfs_visited)) return true;
            }
            
            // If dfs visited is marked as true then return true
            else if(dfs_visited[nbrs])
            {
                return true;
            }
        }
        
        // Else while returning from recursion call dismark the dfs_visited entry
        dfs_visited[node]=0;
        
        // Else return false
        return false;

    }

    bool isCyclic(int n, vector<int> adj[]) 
    {
       // Initial values assignment
       int vis[n], dfs_visited[n];
       memset(vis,0, sizeof vis);
       memset(vis,0, sizeof dfs_visited);
       
       // Travel for each component
       for(int i=0;i<n;i++)
       {
           // If not visited then call the method
           if(!vis[i])
           {
               if(checkCycle(i,adj,vis,dfs_visited)) return true ;
           }
       }
       
       // If no cycle then return false
       return false;  
    }
};
 ```
	    
