## **Graph representation in c++**

**n → number of nodes**

**m → number of edges**

**Two was to store** 

- **Matrix way**
- **List way**

```cpp
**// if the matrix is 0 based indexing then take
int adj[n][n]
// if 1 based indexing 
int adj[n+1][n+1]**
```

### **Way to implement adjacency matrix**

```cpp
**int main(){
int n,m;
cin>>n>>m;
int adj[n+1][n+1];

for(int i=0;i<m;i++){
    int u,v;
    cin>>u>>v;
    adj[u][v]=1;
    adj[v][u]=1;
}

return 0;
}**
```

## **Adjacency list**

**→ It takes O(2* no of edges) as space complexity → In undirected graph**

**→ O(no of edges) → In directed graph**

## **Visited array → The array which will be marked 0’s**

**We say it as 1 when we get the targeted node one by one by each level of search**    

## **BFS Traversal → Breadth wise traversal**

**BFS using queue**

**Keep taking out till the queue is empty**

**→ go to node, take out the neighbours from adjacency list, push into the queue, mark the visited array as 1** 

**Space complexity - O(n)**

**Time complexity - O( n) + O(2*E)**