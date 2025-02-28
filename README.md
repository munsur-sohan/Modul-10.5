# Modul-10.5
# Que:1.Bellman-Ford;
ector<int> bellmanFord(int V, vector<vector<int>>& edges, int src) {
        int e=edges.size();
        vector<int> dis(V,1e8);
        dis[src]=0;
        for(int i=0;i<V-1;i++)
        {
            for(int j=0;j<e;j++)
            {
                int a=edges[j][0];
                int b=edges[j][1];
                int c=edges[j][2];
                if(dis[a]!=1e8 && dis[a]+c<dis[b]){
                 dis[b]=dis[a]+c;
                }
            }
            
        }
            for(int j=0;j<e;j++)
            {
                int a=edges[j][0];
                int b=edges[j][1];
                int c=edges[j][2];
                if(dis[a]!=1e8 && dis[a]+c<dis[b]){
                 return{-1};
                }
            }
            return dis;
    }
};
