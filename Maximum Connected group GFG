class Solution {
    int dfs(int[][] grid, int i, int j, int n, int islandNo) {
        if (i < 0 || j < 0 || i >= n || j >= n || grid[i][j] == 0 || grid[i][j] == islandNo) {
            return 0;
        }
        grid[i][j] = islandNo;
        int a = dfs(grid, i - 1, j, n, islandNo);
        int b = dfs(grid, i, j - 1, n, islandNo);
        int c = dfs(grid, i + 1, j, n, islandNo);
        int d = dfs(grid, i, j + 1, n, islandNo);
        return a + b + c + d + 1;
    }

    public int MaxConnection(int[][] grid) {
        int n = grid.length;
        int islandNo = 2;  // Start labeling islands from 2
        int ans = 0;
        Map<Integer, Integer> map = new HashMap<>();
        
        // First pass: identify and label all islands with unique numbers and store their sizes
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == 1) {
                    int size = dfs(grid, i, j, n, islandNo);
                    map.put(islandNo, size);
                    ans = Math.max(ans, size);
                    islandNo++;
                }
            }
        }
        
        // Second pass: check each zero and see if flipping it connects the maximum number of islands
        for (int i = 0; i < n; i++) {
            for (int j = 0; j < n; j++) {
                if (grid[i][j] == 0) {
                    Set<Integer> set = new HashSet<>();
                    if (i > 0 && grid[i - 1][j] > 1) {
                        set.add(grid[i - 1][j]);
                    }
                    if (i < n - 1 && grid[i + 1][j] > 1) {
                        set.add(grid[i + 1][j]);
                    }
                    if (j > 0 && grid[i][j - 1] > 1) {
                        set.add(grid[i][j - 1]);
                    }
                    if (j < n - 1 && grid[i][j + 1] > 1) {
                        set.add(grid[i][j + 1]);
                    }
                    int maxSize = 1;  // Start with 1 to account for the flipped cell itself
                    for (Integer s : set) {
                        maxSize += map.get(s);
                    }
                    ans = Math.max(maxSize, ans);
                }
            }
        }
        return ans;
    }
}
