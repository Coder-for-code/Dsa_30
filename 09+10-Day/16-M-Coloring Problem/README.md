# 16-[M-Coloring Problem](https://practice.geeksforgeeks.org/problems/m-coloring-problem-1587115620/1#)

<div class="problem-statement">
                <p></p><p><span style="font-size:18px">Given an undirected graph and an integer&nbsp;<strong>M</strong>. The task is to determine if the graph can be colored with at most M&nbsp;colors such that no two adjacent vertices of the graph are colored with the same color. Here coloring of a graph means the assignment of colors to all vertices. Print 1&nbsp;if it is possible to colour vertices and 0&nbsp;otherwise.</span></p>

<p><span style="font-size:18px"><strong>Example 1:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input:
</strong>N = 4
M = 3
E = 5
Edges[] = {(0,1),(1,2),(2,3),(3,0),(0,2)}
<strong>Output: </strong>1<strong>
Explanation: </strong>It is possible to colour the
given graph using 3 colours.</span>
</pre>

<p><span style="font-size:18px"><strong>Example 2:</strong></span></p>

<pre><span style="font-size:18px"><strong>Input:
</strong>N = 3
M = 2
E = 3
Edges[] = {(0,1),(1,2),(0,2)}
<strong>Output: </strong>0</span></pre>

<p><span style="font-size:18px"><strong>Your Task:</strong><br>
Your task is to complete the function&nbsp;<strong>graphColoring()</strong>&nbsp;which takes the 2d-array graph[], the number of colours and the number of nodes&nbsp;as inputs and returns <strong>true</strong>&nbsp;if answer exists otherwise <strong>false</strong>. 1 is printed if the returned value is&nbsp;<strong>true,&nbsp;</strong>0 otherwise. The printing is done by the driver's code.<br>
<strong>Note</strong>: In Example there are Edges not the graph.Graph will be like, if there is an edge between vertex X and vertex Y graph[] will contain 1 at graph[X-1][Y-1], else 0.&nbsp;In 2d-array graph[ ], nodes are 0-based indexed, i.e. from 0 to N-1.Function will be contain 2-D graph not the edges.</span><br>
<br>
<strong><span style="font-size:18px">Expected Time Complexity:</span></strong><span style="font-size:18px">&nbsp;O(M</span><sup>N</sup><span style="font-size:18px">).</span><br>
<strong><span style="font-size:18px">Expected Auxiliary&nbsp;</span></strong><span style="font-size:18px"><strong>Space:</strong>&nbsp;O(N).</span></p>

<p><span style="font-size:18px"><strong>Constraints:</strong><br>
1 ≤ N ≤ 20<br>
1 ≤ E ≤ (N*(N-1))/2<br>
1 ≤ M ≤ N</span></p>
 <p></p>
            </div>
	    
## Video Notes

![vlcsnap-2022-07-10-22h16m44s984](https://user-images.githubusercontent.com/37560890/178155320-a1825ba8-4687-470b-9f85-1bb6ff8b63ab.png)
![vlcsnap-2022-07-10-22h18m25s299](https://user-images.githubusercontent.com/37560890/178155322-0f8ae821-f3b7-4dae-b8f2-840d32301b7f.png)
![vlcsnap-2022-07-10-22h18m59s226](https://user-images.githubusercontent.com/37560890/178155324-bd785fc4-1430-4770-a27b-8e2f038a33a0.png)
![vlcsnap-2022-07-10-22h22m34s632](https://user-images.githubusercontent.com/37560890/178155325-d94ea80d-9ad4-47bc-a249-cd8033ee408e.png)
![vlcsnap-2022-07-10-22h23m10s086](https://user-images.githubusercontent.com/37560890/178155327-9d1175af-94c7-484f-b54a-52caa0a6d149.png)
![vlcsnap-2022-07-10-22h24m23s543](https://user-images.githubusercontent.com/37560890/178155328-eddffa95-771e-4cf9-9aa6-02ff42728e15.png)
![vlcsnap-2022-07-10-22h24m31s271](https://user-images.githubusercontent.com/37560890/178155331-d85e693c-604f-43be-b11f-24cacf341679.png)
![vlcsnap-2022-07-10-22h27m46s701](https://user-images.githubusercontent.com/37560890/178155332-7bbde93e-4223-4b19-9aa8-0f8970814157.png)
![vlcsnap-2022-07-10-22h28m02s654](https://user-images.githubusercontent.com/37560890/178155333-b5885726-2cac-462b-ad21-4474a8cbe85f.png)
![vlcsnap-2022-07-10-22h28m38s998](https://user-images.githubusercontent.com/37560890/178155334-331e2823-e975-4ef3-9b3e-2e492307c765.png)
![vlcsnap-2022-07-10-22h30m58s063](https://user-images.githubusercontent.com/37560890/178155335-3505c9dd-c532-4b3d-89cd-2aec3bd3f1f9.png)
![vlcsnap-2022-07-10-22h41m21s474](https://user-images.githubusercontent.com/37560890/178155336-700fa204-1a0d-42db-ba6c-33786916b60b.png)

## Solution 1. Backtracking
```cpp

// Expected Time Complexity: O(M^N).
// Expected Auxiliary Space: O(N).

bool is_safe(int node,int color[],bool graph[101][101],int n , int col)
{
    // Travel for all it's adjacent nodes in a matrix
    for(int k=0;k<n;k++)
    {
        // Check self node, Adj node , Color of adj == col then return false
        if(k!=node and graph[node][k]==1 and color[k]==col) return false;
    }
    return true;
}

bool solve(int node,int color[],int m, int n, bool graph[101][101])
{
    // If the node is equal to n then return true
    if(node==n) return true;
    
    // Try out every color from 1 to m
    for(int i=1; i<=m;i++)
    {
        if(is_safe(node,color,graph,n,i))
        {
            // If is safe then color that node with i
            color[node]=i;
            
            // Call for the next node
            if(solve(node+1,color,m,n,graph)) return true;
            
            // Backtracking step
            color[node]=0;
        }
        
        // If no color possible then retun false
        return false;
    }
}


bool graphColoring(bool graph[101][101], int m, int n)
{
    // Create the color array and make all the entires to 0
    int color[n]= {0};
    
    // Calling the recursive function
    if(solve(0,color,m,n,graph)) return true;
    
    // Return false if not possible
    return false;
    
    
}

```
or

```cpp

// Expected Time Complexity: O(M^N).
// Expected Auxiliary Space: O(N).

bool isPossible(bool graph[101][101],int color[],int N,int col,int node)
{
    for(int k=0;k<N;k++)
    {
        if(k!=node && graph[node][k]==1 && color[k]==col) return false;
    }
    return true;
}

bool solve(bool graph[101][101],int m,int N,int color[],int node)
{
    if(node==N)
        return true;
        
    // traverse onto diff color recursively
    for(int i=1;i<=m;i++)
    {
        if(isPossible(graph,color,N,i,node))
        {
            color[node]=i;
            if(solve(graph,m,N,color,node+1)) return true;
            color[node]=0;
        }
            
    }
    return false;
}

bool graphColoring(bool graph[101][101], int m, int N)
{
    int color[N];
    memset(color,0,sizeof color);
    if(solve(graph,m,N,color,0)) return true;
    return false;
}
```
