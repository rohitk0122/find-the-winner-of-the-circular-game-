# find-the-winner-of-the-circular-game-
import java.util.LinkedList;
import java.util.List;

class Solution {
    public int findTheWinner(int n, int k) {
        List<Integer> friends = new LinkedList<>();  // Initialize the list
        for (int i = 1; i <= n; i++) {
            friends.add(i);
        }
        
        int currentIndex = 0;
        
        // Simulate the game
        while (friends.size() > 1) {
            // Find the index of the friend who loses the game
            currentIndex = (currentIndex + k - 1) % friends.size();
            friends.remove(currentIndex);
        }
        
        // The last remaining friend is the winner
        return friends.get(0);
    }
    
    public static void main(String[] args) {
        Solution solution = new Solution();
        int n = 5;
        int k = 2;
        System.out.println("The winner is: " + solution.findTheWinner(n, k));  // Output should be 3
    }
}
