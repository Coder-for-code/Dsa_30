## 20-[Union-Find](https://practice.geeksforgeeks.org/problems/union-find/1/)

<div class="problem-statement">
                <p></p><p><span style="font-size:18px">This problem is to implement disjoint set union. There will be 2 incomplete functions namely union and find. You have to complete these functions.&nbsp;</span></p>

<p><span style="font-size:18px"><strong>Union:</strong> Join two subsets into a single set.<br>
<strong>isConnected:</strong> Determine which subset a particular element is in. This can be used for determining if two elements are in same subset.</span></p>

<p><span style="font-size:18px"><strong>Example 1:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input:
</strong>N = 5
q = 4
Queries = 
Union(1,3)
isConnected(1,2)
Union(1,5)
isConnected(3,5)
<strong>Output:
</strong>0
1<strong>
Explanation: </strong>Initially all nodes 1 2 3 4 5
are not connected.&nbsp;
After <strong>Union(1,3)</strong>, node 1 and 3 will be
connected.
When we do <strong>isConnected(</strong><strong>1,2)</strong>,&nbsp; as node 1
and 2&nbsp;are not connected it will return 0.
After <strong>Union(1,5)</strong>, node 1 and 5&nbsp;will be
connected.
When we do <strong>isConnected(3,5</strong><strong>)</strong>,&nbsp; as node
1 and 3&nbsp;are&nbsp;connected, and node 1 and 5
are connected, hence 3 and 5 are
connected.&nbsp;Thus it will return 1.</span></pre>

<p><span style="font-size:18px"><strong>Example 2:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input:
</strong>N = 5
q = 4
Queries = 
Union(1,4)
Union(1,5)
isConnected(2,3)
Union(3,4)
<strong>Output: </strong>0</span>
</pre>

<p><span style="font-size:18px"><strong>Your Task:</strong></span></p>

<p><span style="font-size:18px">You have to complete the function <strong>union_() </strong>which merges the node1 and node2. You will also have to complete the function <strong>isConnected() </strong>which will return whether the two nodes are connected.</span></p>

<p><strong><span style="font-size:18px">Note:&nbsp;</span></strong><span style="font-size:18px">Both function will contain two arrays&nbsp;<strong>par[] and ranks1[]&nbsp;</strong>along with two nodes. Initially&nbsp;<strong>par[i] = i </strong>and <strong>rank1[i] = 1&nbsp;</strong></span></p>

<p><span style="font-size:18px"><strong>Expected Time Complexity:</strong>&nbsp;O(N + Q).<br>
<strong>Expected Auxiliary Space:</strong>&nbsp;O(1).</span></p>

<p><span style="font-size:18px"><strong>Constraints:&nbsp;</strong><br>
1 &lt;= N &lt;= 10<sup>5</sup><br>
1&lt;= Q &lt;= 10<sup>5</sup><br>
1 &lt;= node1, node2 &lt;= N</span></p>
 <p></p>
            </div>
	    
## Video Notes

![vlcsnap-2022-06-10-21h10m27s044](https://user-images.githubusercontent.com/37560890/173118413-c1855c19-46ff-46fd-a301-8c6ec42a74a1.png)
![vlcsnap-2022-06-10-21h17m50s699](https://user-images.githubusercontent.com/37560890/173118418-ddde1bfe-5859-4380-95c4-0e11e7001c50.png)
![vlcsnap-2022-06-10-21h30m56s093](https://user-images.githubusercontent.com/37560890/173118423-a2871845-92fd-4283-83be-f7171353aeba.png)
![vlcsnap-2022-06-10-22h02m46s666](https://user-images.githubusercontent.com/37560890/173118424-16245dd7-aa7c-4631-9ea4-c041bc2161af.png)
![vlcsnap-2022-06-10-22h04m34s906](https://user-images.githubusercontent.com/37560890/173118425-f6a88d89-e57b-4ab6-9214-31f1c87807c3.png)
![vlcsnap-2022-06-10-22h05m40s626](https://user-images.githubusercontent.com/37560890/173118427-f33e4986-cbff-4b52-9952-d2d60a3d984c.png)
![vlcsnap-2022-06-10-22h07m25s716](https://user-images.githubusercontent.com/37560890/173118429-1c62683e-9f9a-45c0-a77e-d74fe49c613c.png)
![vlcsnap-2022-06-10-22h08m09s020](https://user-images.githubusercontent.com/37560890/173118432-c919255f-d424-41b2-a5fb-daf7992222a4.png)
![vlcsnap-2022-06-10-22h08m47s664](https://user-images.githubusercontent.com/37560890/173118437-8d2b7e0b-e3cb-4d85-89df-d371a631c41c.png)
![vlcsnap-2022-06-10-22h09m36s286](https://user-images.githubusercontent.com/37560890/173118440-8f66c833-d57d-463a-a7bd-6547e755025c.png)
![vlcsnap-2022-06-10-22h10m01s616](https://user-images.githubusercontent.com/37560890/173118442-dfd4e3a9-ca0a-4c2d-8cbf-5b97efeeb22d.png)
![vlcsnap-2022-06-10-22h10m15s975](https://user-images.githubusercontent.com/37560890/173118444-9826a155-798f-45be-9a88-5f606d66fc9b.png)
![vlcsnap-2022-06-10-22h11m01s821](https://user-images.githubusercontent.com/37560890/173118447-ee02f020-8274-4d9d-b69b-190ceeb93d39.png)
![vlcsnap-2022-06-10-22h11m21s849](https://user-images.githubusercontent.com/37560890/173118449-de665802-d0be-498f-904a-796566191ee5.png)
![vlcsnap-2022-06-10-22h12m26s046](https://user-images.githubusercontent.com/37560890/173118452-3eadffde-e0cf-4bd6-84c2-f45e9845c37b.png)
![vlcsnap-2022-06-10-22h14m12s256](https://user-images.githubusercontent.com/37560890/173118454-1f3bc2a1-8c8b-4d0d-a6a3-83b124b8901b.png)
![vlcsnap-2022-06-10-22h20m34s269](https://user-images.githubusercontent.com/37560890/173118456-6ce13475-e782-4625-8cc3-39c5400e8248.png)
![vlcsnap-2022-06-10-22h20m57s234](https://user-images.githubusercontent.com/37560890/173118459-f5680486-d2f0-4bdf-8701-160060ce9825.png)
![vlcsnap-2022-06-10-22h42m57s329](https://user-images.githubusercontent.com/37560890/173118462-6ddb5253-ef8a-423f-9d95-4433e958f10e.png)

```cpp
class Solution
{
    public:
    //Function to merge two nodes a and b.
    
    int find_parent(int node,int par[])
    {
        // If the same node is a parent then return the same node as parent
        if(par[node]== node) return node;
        
        // Else find parent and store the parent for rank compression
        return par[node]= find_parent(par[node],par);
    }
    
    void union_( int a, int b, int par[], int rank1[]) 
    {
        //code here
        
        // Find the parent of both the nodes
        int u= find_parent(a,par);
        int v= find_parent(b,par);
        
        // If the rank of u is less then the rank of v
        // Then attach it to v
        if(rank1[u] < rank1[v]) par[u]= v;
        else if(rank1[v] < rank1[u]) par[v]= u;
        
        // If both the ranks are equal then attach anyone to the other 
        // And increment the rank accordingly
        else 
        {
            par[v] =u;
            rank1[u]++;
        }
        
        
    }
    
    //Function to check whether 2 nodes are connected or not.
    bool isConnected(int x,int y, int par[], int rank1[])
    {
        //code here
        return find_parent(x,par)== find_parent(y,par);
    }
};
```
