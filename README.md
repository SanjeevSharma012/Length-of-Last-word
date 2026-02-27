Find Length of Last Word (Java)

This project contains a Java solution to find the length of the last word in a given string.

📌 Problem Statement

Given a string s consisting of words and spaces, return the length of the last word in the string.

A word is defined as a sequence of non-space characters.

The string may contain leading or trailing spaces.

💡 Approach

Remove leading and trailing spaces using trim().

Split the string using " " (space) as delimiter.

Access the last word from the array.

Return the length of that word.

🧠 Java Solution
// User function Template for Java
class Solution {
    int findLength(String s) {
        // Remove extra spaces
        String[] ans = s.trim().split(" ");
        
        // Get last word
        String word = ans[ans.length - 1];
        
        // Return its length
        return word.length();
    }
}
🧪 Example
Input:
"Hello World"
Output:
5
Explanation:

The last word is "World" and its length is 5.

⚡ Time & Space Complexity

Time Complexity: O(n)

Space Complexity: O(n) (due to split array)

🚀 Optimized Version (Without Extra Space)

Instead of using split(), we can solve it in O(1) space:

class Solution {
    int findLength(String s) {
        int length = 0;
        int i = s.length() - 1;

        // Skip trailing spaces
        while (i >= 0 && s.charAt(i) == ' ') {
            i--;
        }

        // Count characters of last word
        while (i >= 0 && s.charAt(i) != ' ') {
            length++;
            i--;
        }

        return length;
    }
}

Time Complexity: O(n)

Space Complexity: O(1).
