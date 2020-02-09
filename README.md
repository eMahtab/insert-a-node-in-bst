# Insert a node in a Binary Search Tree(BST)
## https://leetcode.com/problems/insert-into-a-binary-search-tree

Given the root node of a binary search tree (BST) and a value to be inserted into the tree, insert the value into the BST. Return the root node of the BST after the insertion. It is guaranteed that the new value does not exist in the original BST.

Note that there may exist multiple valid ways for the insertion, as long as the tree remains a BST after insertion. You can return any of them.
```
For example, 

Given the tree:
        4
       / \
      2   7
     / \
    1   3
And the value to insert: 5
You can return this binary search tree:

         4
       /   \
      2     7
     / \   /
    1   3 5

This tree is also valid:

         5
       /   \
      2     7
     / \   
    1   3
         \
          4
```

## Implementation : Iterative

```java
/**
 * Definition for a binary tree node.
 * public class TreeNode {
 *     int val;
 *     TreeNode left;
 *     TreeNode right;
 *     TreeNode(int x) { val = x; }
 * }
 */
class Solution {
    public TreeNode insertIntoBST(TreeNode root, int val) {
        TreeNode node = new TreeNode(val);
        if(root == null)
            return node;
        TreeNode parent = null;
        TreeNode current = root;
        while(current != null){
            parent = current;
            if(val < current.val)
                current = current.left;
            else
                current = current.right;
        }
        if(val < parent.val)
            parent.left = node;
        else
            parent.right = node;
        
        return root; 
    }
}
```

# References :
https://www.youtube.com/watch?v=bmaeYtlO2OE
