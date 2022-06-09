## 13-[Detect cycle in a directed graph](https://practice.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1/#)

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
    // Function to detect cycle in a directed graph.
    bool isCyclic(int V, vector<int> adj[]) 
    {
        // Make a indegree vector and set it to 0
        int inDegree[V]={0};
        
        // Compute the indegree
        for(int i=0; i<V; i++)
        {
            for(int it: adj[i])
            {
                inDegree[it]++;
            }
        }
        
        // Make a queue for processing
        queue<int> q;
        
        // Edge case
        for(int i=0; i<V; i++)
        {
            if(inDegree[i]==0) q.push(i);
        }
        
        // Counter for comparison
        int cnt=0;
        
        // Main logic of kahn's algorithm
        while(!q.empty())
        {
            int v = q.front();
            q.pop();
            cnt++;
        
            // If the indegree is 0 then push into the queue
            for(int it: adj[v])
            {
                if(--inDegree[it]==0)
                    q.push(it);
            }
        }
        
        // Finally if the node of nodes == count then return 0 else 1
        if(cnt==V)return 0;
        else return 1;
    }
};
```
	    
