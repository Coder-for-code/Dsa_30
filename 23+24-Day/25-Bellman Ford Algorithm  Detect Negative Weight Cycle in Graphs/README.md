## 25-[Negative weight cycle Bellman Ford Algorithm](https://practice.geeksforgeeks.org/problems/negative-weight-cycle3504/1#)

<div class="problem-statement">
                <p></p><p><span style="font-size:18px">Given a weighted directed graph with n nodes and m edges. Nodes are labeled from 0 to n-1, the task is to check if it contains a negative weight cycle or not.<br>
<strong>Note:&nbsp;</strong>edges[i] is&nbsp;defined as u, v and weight.</span><br>
&nbsp;</p>

<p><span style="font-size:18px"><strong>Example 1:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input: </strong>n = 3, edges = {{0,1,-1},{1,2,-2},
{2,0,-3}}
<strong>Output: </strong>1
<strong>Explanation: </strong>The graph contains negative weight
cycle as 0-&gt;1-&gt;2-&gt;0 with weight -1,-2,-3.</span>
</pre>

<p><span style="font-size:18px"><strong>Example 2:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input: </strong>n = 3, edges = {{0,1,-1},{1,2,-2},
{2,0,3}}
<strong>Output: </strong>0
<strong>Explanation: </strong>The graph does not contain any
negative weight cycle.</span>
</pre>

<p>&nbsp;</p>

<p><span style="font-size:18px"><strong>Your Task:</strong><br>
You don't need to read or print anyhting. Your task is to complete the function&nbsp;<strong>isNegativeWeightCycle()&nbsp;</strong>which takes n and edges as input paramater and returns 1 if graph contains negative weight cycle otherwise returns 0.</span><br>
&nbsp;</p>

<p><span style="font-size:18px"><strong>Expected Time Complexity:&nbsp;</strong>O(n*m)<br>
<strong>Expected Space Compelxity:&nbsp;</strong>O(n)</span><br>
&nbsp;</p>

<p><span style="font-size:18px"><strong>Constraints:</strong><br>
1 &lt;= n &lt;= 100<br>
1 &lt;= m &lt;= n*(n-1)</span><span style="font-size:18px">, where m is the total number of Edges in the directed graph.</span></p>
 <p></p>
            </div>


## Video Notes

![vlcsnap-2022-06-11-21h49m15s544](https://user-images.githubusercontent.com/37560890/173199717-9a4d9e6c-cc3a-4481-b309-d2e40402d1dc.png)
![vlcsnap-2022-06-11-21h52m50s365](https://user-images.githubusercontent.com/37560890/173199719-688c18ae-8882-471f-8902-901f38504696.png)
![vlcsnap-2022-06-11-21h53m27s132](https://user-images.githubusercontent.com/37560890/173199720-df0699f8-2049-40e7-b20a-1a2679aa542f.png)
![vlcsnap-2022-06-11-21h54m34s621](https://user-images.githubusercontent.com/37560890/173199721-d4d2d5f0-3731-4ba9-82db-d3be5f10c9ef.png)
![vlcsnap-2022-06-11-21h58m16s093](https://user-images.githubusercontent.com/37560890/173199722-9cfc3083-fc54-46cc-90ad-7d32b5ce8447.png)
![vlcsnap-2022-06-11-22h37m21s150](https://user-images.githubusercontent.com/37560890/173199723-04c96b3a-4827-45e5-a61c-6552ece970c2.png)
![vlcsnap-2022-06-11-22h38m27s855](https://user-images.githubusercontent.com/37560890/173199725-5ece3980-294e-48ee-8bd5-94ec6059b589.png)
![vlcsnap-2022-06-11-23h11m22s938](https://user-images.githubusercontent.com/37560890/173199726-14e03c83-c61e-4576-9380-d0cfcaa77299.png)
![vlcsnap-2022-06-11-23h13m03s520](https://user-images.githubusercontent.com/37560890/173199727-222f28e2-517f-4d12-b3b3-d262b18b3fc2.png)
![vlcsnap-2022-06-11-23h19m21s117](https://user-images.githubusercontent.com/37560890/173199728-e9beca94-debf-446b-af27-0904f46fc3a4.png)
![vlcsnap-2022-06-11-23h21m00s064](https://user-images.githubusercontent.com/37560890/173199730-53850e9e-fd27-4b7a-a95b-b69292186a36.png)
![vlcsnap-2022-06-11-23h21m28s411](https://user-images.githubusercontent.com/37560890/173199731-edb32c41-9d00-4864-8aa0-4a219c4b59b0.png)
![vlcsnap-2022-06-11-23h22m07s416](https://user-images.githubusercontent.com/37560890/173199734-7b2957b4-75a7-4541-99c3-081a97582bba.png)
![vlcsnap-2022-06-11-23h23m05s081](https://user-images.githubusercontent.com/37560890/173199736-052a103d-97ea-4e86-992a-2815c0c7a4d7.png)
![vlcsnap-2022-06-11-23h23m24s852](https://user-images.githubusercontent.com/37560890/173199737-100d6ff3-adcf-4641-8f5f-8e2c48b04820.png)
![vlcsnap-2022-06-11-23h24m09s782](https://user-images.githubusercontent.com/37560890/173199738-a5b8a8bb-fee5-4d9e-bcb9-9edf51fdb464.png)
![vlcsnap-2022-06-11-23h24m35s664](https://user-images.githubusercontent.com/37560890/173199740-ad52b829-9914-4fe8-89ca-3acce490a4b4.png)
![vlcsnap-2022-06-11-23h25m21s130](https://user-images.githubusercontent.com/37560890/173199742-1af23ae3-cd77-499a-835a-fd3c5a3323c7.png)
![vlcsnap-2022-06-11-23h25m31s017](https://user-images.githubusercontent.com/37560890/173199743-7efcf00c-ac50-4e89-b8fb-aad9a9ff562c.png)
![vlcsnap-2022-06-11-23h28m07s118](https://user-images.githubusercontent.com/37560890/173199744-e677d457-e047-4739-a3e5-1c30af332ae1.png)
![vlcsnap-2022-06-11-23h29m35s926](https://user-images.githubusercontent.com/37560890/173199745-9698f3d5-222e-43a8-94dc-eca6eac7f9ff.png)


```cpp
class Solution 
{
public:
	int isNegativeWeightCycle(int n, vector<vector<int>>edges)
	{
	    vector<pair<int,pair<int,int>>> adj;
	    
	    for(int i=0;i<edges.size();i++)
	    {
	        int u=edges[i][0];
            int v=edges[i][1];
            int w=edges[i][2];
            adj.push_back({u,{v,w}});
	    }
	    
	    vector<int> dist(n,1e6+7);
	    dist[0]=0;
	    
	    for(int i=0;i<n-1;i++)
	    {
	        for(auto edge:adj)
	        {
	            int u=edge.first;
	            int v=edge.second.first;
	            int w=edge.second.second;
	            
	            if(dist[v]>dist[u]+w)
	            {
	                
	                dist[v]=dist[u]+w;
	            }
	        }
	    }
	    
        for(auto edge:adj)
        {
            int u=edge.first;
            int v=edge.second.first;
            int w=edge.second.second;
             // cout<<u<<" "<<v<<" "<<w<<endl;

            if(dist[v]>dist[u]+w)
            {
                // cout<<"h";
                return 1;
            }
        }
        
	    return 0;
	}
};

```
