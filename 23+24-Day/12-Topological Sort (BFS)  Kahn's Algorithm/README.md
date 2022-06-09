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

![vlcsnap-2022-06-08-19h59m23s211](https://user-images.githubusercontent.com/37560890/172690088-15be8037-3978-48e8-bf7a-bab4f5f7656f.png)
![vlcsnap-2022-06-08-20h43m14s747](https://user-images.githubusercontent.com/37560890/172690094-764d7e01-7ce5-4db2-a54d-66675396746e.png)
![vlcsnap-2022-06-08-20h45m07s226](https://user-images.githubusercontent.com/37560890/172690097-e3521fca-b776-4334-b4ef-01cff60126e3.png)
![vlcsnap-2022-06-08-23h43m01s847](https://user-images.githubusercontent.com/37560890/172690101-bd67c0a3-ddfd-4b8a-b4bc-725f50d048ab.png)
![vlcsnap-2022-06-08-23h44m43s224](https://user-images.githubusercontent.com/37560890/172690102-a0e19919-115c-4ac3-a358-155d064e7770.png)
![vlcsnap-2022-06-08-23h52m34s684](https://user-images.githubusercontent.com/37560890/172690103-5169d900-f66a-4847-a66e-1b6713f88f77.png)

```cpp

class Solution
{
	public:
	//Function to return list containing vertices in Topological order. 
	vector<int> topoSort(int n, vector<int> adj[]) 
	{
       queue<int> q;
       vector<int> indegree(n,0);
       
       // Compute the indegree
       for(int i=0;i<n;i++)
       {
           for(auto it: adj[i])
           {
               indegree[it]++;
           }
       }
       
       // Check if the indegree is 0 then push into queue
       for(int i=0;i<n;i++)
       {
           if(indegree[i]==0)
           {
               q.push(i);
           }
       }
       
       // If indegree is not 0 then
       vector<int> topo;
       while(!q.empty())
       {
           int node= q.front();
           q.pop();
           topo.push_back(node);
           
           for(auto it: adj[node])
           {
               indegree[it]--;
               
               if(indegree[it]==0)
               {
                   q.push(it);
               }
           }
       }
       return topo;
	}
	
};

```
