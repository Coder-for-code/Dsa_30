## 10-[Detect cycle in a directed graph](https://practice.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1/#)

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
 
 ## Video Notes
 
![vlcsnap-2022-06-08-18h07m41s578](https://user-images.githubusercontent.com/37560890/172640821-4dac4f11-b522-44b9-8658-c3da8071e8fb.png)
![vlcsnap-2022-06-08-18h09m19s835](https://user-images.githubusercontent.com/37560890/172640832-0271c1e4-d383-4132-80b3-392f416f4678.png)
![vlcsnap-2022-06-08-18h12m24s263](https://user-images.githubusercontent.com/37560890/172640836-489e78a3-5a26-40d2-b3ef-6f115fc1776f.png)
![vlcsnap-2022-06-08-18h16m01s742](https://user-images.githubusercontent.com/37560890/172640842-19d6ec99-0c70-4c24-bbd1-870e72ffd364.png)
![vlcsnap-2022-06-08-18h16m03s388](https://user-images.githubusercontent.com/37560890/172640846-9b0108aa-6615-4fe0-b1bf-4e1787cad29d.png)
![vlcsnap-2022-06-08-18h17m49s362](https://user-images.githubusercontent.com/37560890/172640852-1f91bbb5-c31c-470e-9e5e-29d6d39ca61d.png)
![vlcsnap-2022-06-08-18h20m56s145](https://user-images.githubusercontent.com/37560890/172640858-cd09ba62-98de-409b-8309-018f4f3b03b1.png)
![vlcsnap-2022-06-08-18h53m30s043](https://user-images.githubusercontent.com/37560890/172640863-e7db67e9-727b-438c-bfbf-46867fdefdf7.png)
![vlcsnap-2022-06-08-18h54m08s938](https://user-images.githubusercontent.com/37560890/172640866-11a742df-bb96-4cd0-a229-7913174277ff.png)
![vlcsnap-2022-06-08-18h56m56s195](https://user-images.githubusercontent.com/37560890/172640872-fe7c2227-da43-4174-a6c6-bbf7de49b2bd.png)
![vlcsnap-2022-06-08-18h57m05s497](https://user-images.githubusercontent.com/37560890/172640878-5dc4d169-760b-4acf-a982-eaf84906993e.png)

 
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
	    
