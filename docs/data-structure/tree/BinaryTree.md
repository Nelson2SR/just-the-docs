---
layout: default
title: BinaryTree
parent: Tree
published: true
comments: true
---

# BinaryTree

## Find Minimun Depth of a Binary Tree ([Link](https://www.geeksforgeeks.org/find-minimum-depth-of-a-binary-tree/))

```java
/* Java implementation to find minimum depth 
   of a given Binary tree */
  
/* Class containing left and right child of current 
node and key value*/
class Node 
{ 
    int data; 
    Node left, right; 
    public Node(int item) 
    { 
        data = item; 
        left = right = null; 
    } 
} 
public class BinaryTree 
{ 
    //Root of the Binary Tree 
    Node root; 
  
    int minimumDepth() 
    { 
        return minimumDepth(root); 
    } 
  
    /* Function to calculate the minimum depth of the tree */
    int minimumDepth(Node root) 
    { 
        // Corner case. Should never be hit unless the code is 
        // called on root = NULL 
        if (root == null) 
            return 0; 
  
        // Base case : Leaf Node. This accounts for height = 1. 
        if (root.left == null && root.right == null) 
            return 1; 
  
        // If left subtree is NULL, recur for right subtree 
        if (root.left == null) 
            return minimumDepth(root.right) + 1; 
  
        // If right subtree is NULL, recur for left subtree 
        if (root.right == null) 
            return minimumDepth(root.left) + 1; 
  
        return Math.min(minimumDepth(root.left), 
                        minimumDepth(root.right)) + 1; 
    } 
  
    /* Driver program to test above functions */
    public static void main(String args[]) 
    { 
        BinaryTree tree = new BinaryTree(); 
        tree.root = new Node(1); 
        tree.root.left = new Node(2); 
        tree.root.right = new Node(3); 
        tree.root.left.left = new Node(4); 
        tree.root.left.right = new Node(5); 
  
        System.out.println("The minimum depth of "+ 
          "binary tree is : " + tree.minimumDepth()); 
    } 
} 
}
```

## Maximum Path Sum in a Binary Tree ([Link](https://www.geeksforgeeks.org/find-maximum-path-sum-in-a-binary-tree/))

```java
import java.io.*;

class GFG {
	public static void main (String[] args) {
		System.out.println("GfG!");
		BinaryTree tree = new BinaryTree();
		tree.root = new Node(10);
		tree.root.left = new Node(2); 
        tree.root.right = new Node(10); 
        tree.root.left.left = new Node(20); 
        tree.root.left.right = new Node(1); 
        tree.root.right.right = new Node(-25); 
        tree.root.right.right.left = new Node(3); 
        tree.root.right.right.right = new Node(4); 
        System.out.println("maximum path sum is : " + 
                            tree.findMaxSum()); 
	}
}

class Node {
    int data;
    Node left, right;
    
    public Node(int item) {
        data = item;
        left = right = null;
    }
}

class Res {
    public int val;
}

class BinaryTree {
    Node root;
    
    int findMaxSum() {
        return findMaxSum(root);
    }
    
    int findMaxSum(Node node) {
        Res res = new Res();
        res.val = Integer.MIN_VALUE;
        
        findMaxUntil(node, res);
        return res.val;
    }
    
    int findMaxUntil(Node node, Res res) {
        if (node == null){
            return 0;
        }
        
        int l = findMaxUntil(node.left, res);
        int r = findMaxUntil(node.right, res);
        
        int max_single = Math.max(Math.max(l, r) + node.data, node.data);
        
        int max_top = Math.max(max_single, l + r + node.data);
        
        res.val = Math.max(res.val, max_top);
        
        return max_single;
    }
    
}
```