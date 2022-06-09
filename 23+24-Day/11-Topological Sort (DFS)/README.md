## 11-[Topological sort](https://practice.geeksforgeeks.org/problems/topological-sort/1#)
<div class="problem-statement">
                <p></p><p><span style="font-size:18px">Given a Directed Acyclic Graph (DAG) with V vertices and E edges, Find any Topological Sorting of that Graph.

</span></p>

![download](https://user-images.githubusercontent.com/37560890/172689993-cb7d3e92-7cdc-4477-911e-7dba8e1879ff.png)

<p><br>
<span style="font-size:18px"><strong>Example 1:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input:</strong></span>
<strong>Explanation</strong>:
The output 1 denotes that the order is
valid. So, if you have, implemented
your function correctly, then output
would be 1 for all test cases.</span>
<span style="font-size:18px">One possible Topological order for the
graph is 3, 2, 1, 0.</span>
</pre>

<p><span style="font-size:18px"><strong>Example 2:</strong></span></p>

</span><span style="font-size:18px"><strong>Explanation:
</strong></span><span style="font-size:18px">The output 1 denotes that the order is
valid. So, if you have, implemented
your function correctly, then output
would be 1 for all test cases.
One possible Topological order for the
graph is 5, 4, 2, 1, 3, 0.</span></pre>

<p><br>
<span style="font-size:18px"><strong>Your Task:</strong><br>
You don't need to read input or print anything. Your task is to complete the function&nbsp;<strong>topoSort()</strong>&nbsp;</span> <span style="font-size:18px">which takes the integer V denoting the number of vertices and adjacency list as input parameters</span> <span style="font-size:18px"> and returns an array consisting of a the vertices in Topological order. As there are multiple Topological orders possible, you may return any of them. If your returned topo sort is correct then console output will be 1 else 0.</span></p>

<p><br>
<span style="font-size:18px"><strong>Expected Time Complexity:</strong>&nbsp;O(V + E).<br>
<strong>Expected Auxiliary Space:</strong>&nbsp;O(V).</span></p>

<p><br>
<span style="font-size:18px"><strong>Constraints:</strong><br>
2 </span> <span style="font-size:18px">≤</span> <span style="font-size:18px"> V </span> <span style="font-size:18px">≤</span> <span style="font-size:18px">10<sup>4</sup><br>
1 </span> <span style="font-size:18px">≤</span> <span style="font-size:18px"> E </span> <span style="font-size:18px">≤</span> <span style="font-size:18px"> (N*(N-1))/2</span></p>
 <p></p>
            </div>
	    
## Video Notes


![vlcsnap-2022-06-09-11h34m44s014](https://user-images.githubusercontent.com/37560890/172779390-16de48d3-bc52-4b38-a4ff-a537691a3389.png)
![vlcsnap-2022-06-09-11h38m11s994](https://user-images.githubusercontent.com/37560890/172779394-a7a3f5b6-8433-4ef0-a4a5-6a44a81b7ec6.png)
![vlcsnap-2022-06-09-11h39m43s950](https://user-images.githubusercontent.com/37560890/172779397-224fd58d-d5ad-4c2b-8147-3e9d4a6f5396.png)
![vlcsnap-2022-06-09-11h46m45s432](https://user-images.githubusercontent.com/37560890/172779401-ac1017e5-a2c3-417b-9a1c-7ed491c06037.png)
![vlcsnap-2022-06-09-11h47m47s344](https://user-images.githubusercontent.com/37560890/172779403-3a030fb0-3845-4884-be8c-c34cf05c4d7e.png)
![vlcsnap-2022-06-09-11h48m08s301](https://user-images.githubusercontent.com/37560890/172779406-a3f27d9c-5692-42f9-b84f-b9ab686d56a7.png)




```cpp
class Solution
{
	public:
	
	// Helper method
	void find_topo_sort(int node,vector<int> &visited,stack<int> &s, vector<int> adj[])
	{
	    // Mark the visited node as true
	    visited[node]=1;
	    
	    // Visit it's adjacent nbrs
	    for(auto nbrs: adj[node])
	    {
	        if(!visited[nbrs])
	        {
	            find_topo_sort(nbrs,visited,s,adj);
	        }
	    }
	    
	    // Finally push the node into the stack
	    s.push(node);
	}
	
	//Function to return list containing vertices in Topological order. 
	vector<int> topoSort(int n, vector<int> adj[]) 
	{
	    // Define the stack 
	    stack<int> st;
	    
	    // Define the visited array and make initial val to be 0
	    vector<int> visited(n,0);
	    
	    // Travel for each components
	    for(int i=0;i<n;i++)
	    {
	        // If not visited then call the find topo sort
	        if(!visited[i])
	        {
	            find_topo_sort(i,visited,st,adj);
	        }
	    }
	    
	    // Define the ans vector topo
	    vector<int> topo;
	    
	    // Finally pop all the element's from the stack and push into topo vector
	    while(!st.empty())
	    {
	       topo.push_back(st.top()); 
	       st.pop();
	    }
	    
	    // Finally return the ans vector
	    return topo;
	}
};
```
