So in this https://www.geeksforgeeks.org/problems/detect-cycle-in-an-undirected-graph/1 code 
- cycledfs(vector<vector<int>> adj, int src, int visit[], int last) i passed adj directly i.e copying takes place which consumes more space.
- to solve this cycledfs(vector<vector<int>> &adj, int src, int visit[], int last) i used this so here 
    - Pass by Reference: Passed adj by constant reference to avoid unnecessary copying.
- refer https://chatgpt.com/c/67691fb8-2ea4-800e-b757-8005bbe8e264