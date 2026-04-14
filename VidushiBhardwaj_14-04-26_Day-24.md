# Day 24 - POTD

## Problem Description
There is an undirected star graph consisting of n nodes labeled from 1 to n. 
A star graph is a graph where there is one center node and exactly n - 1 edges that connect the center node with every other node.

You are given a 2D integer array edges where each edges[i] = [ui, vi] indicates that there is an edge between the nodes ui and vi. 
Return the center of the given star graph.



## Approach
* The approach begins by taking the two nodes from the first edge:

  * `el1 = edges[0][0]`
  * `el2 = edges[0][1]`
    These are the only possible candidates for the center.

* A loop is used to iterate through the remaining edges starting from index 1.

* For each edge:

  * If `el1` appears in the current edge, it is still a valid candidate for the center, so continue checking.
  * If `el1` does not appear in the current edge, it cannot be the center node.

* In that case, the function immediately returns `el2`, since in a star graph one of the two nodes from the first edge must be the center.

* If the loop completes without eliminating `el1`, then `el1` is returned as the center.

* Key idea:

  * The center node must appear in every edge.
  * Checking only the first two nodes is sufficient due to the structure of a star graph.

* Time Complexity:

  * O(n), where n is the number of edges.

* Space Complexity:

  * O(1), as no extra space is used.




## 👨‍💻 Code

class Solution {
public:
    int findCenter(vector<vector<int>>& edges) {
        int el1=edges[0][0];
        int el2=edges[0][1];

        for(int i=1;i<edges.size();i++){
            if(edges[i][0]==el1 ||edges[i][1]==el1 ){
                continue;
            }else{
                return el2;
                break;
            }

        }

        return el1;
        
    }
};


## 📸 Screenshot

![Solution](VidushiBhardwaj_POTD24.jpg)
