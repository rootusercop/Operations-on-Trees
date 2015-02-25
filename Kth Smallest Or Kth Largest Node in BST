/*
Question: Find the k'th smallest and largest element in a binary search tree.
Question Source: http://www.careercup.com/question?id=15645665
Answer Source: http://geekyjumps.blogspot.com/2013/09/find-kth-largest-element-in-binary.html

Algorithm:
1. For Largest element -> Do a POSTORDER traversal
2. For Smallest element -> Do a PREORDER traversal
*/

package BST.KthSmallestAndLargestNode;

import java.util.Scanner;


public class UsingRecursion { 
	
	private static int index = 0;    // VERY VERY VERY VERY IMP GLOBAL VARIABLE
	
	public static void main(String[] args) {
		
		Scanner in = new Scanner(System.in);
		try{
		
		System.out.println("Enter the number elements of the SORTED array");
		int n = in.nextInt();
		int[] a = new int[n];
		System.out.println("Enter the elements");
		for(int i=0;i<n;i++)
			a[i]=in.nextInt();
		
		Node root = createTree(a,0,a.length-1);
		System.out.println("Enter the kth largest element to be found in the tree");
		int k = in.nextInt();
		System.out.println("The kth smallest element in the tree is: ");
		findKthSmallestNode(root,k);
		index=0;  // reinitialize index to 0
		System.out.println("The kth largest element in the tree is: ");
		findKthLargestNode(root,k);
		}
		finally{
			in.close();
		}
	}
private static void findKthLargestNode(Node root, int k) { 
	// similar to POSTORDER traversal
	
		if(root==null)
			return;
		
		findKthLargestNode(root.right, k);
		if(++index==k){
			System.out.println(root.value);
			return;
		}
		findKthLargestNode(root.left, k);
	}
/*
 * Analysis:
 * Time Complexity = O(n)
 * Space Complexity = O(1)
 */
private static void findKthSmallestNode(Node root, int k) {
	// similar to PREORDER traversal
	
	if(root==null)
		return;
	
	findKthSmallestNode(root.left, k);
	if(++index==k){
		System.out.println(root.value);
		return;
	}
	findKthSmallestNode(root.right, k);
}
/*
 * Analysis:
 * Time Complexity = O(n)
 * Space Complexity = O(1)
 */
public static Node createTree(int[] a,int low, int high) {
	// create tree using sorted array by modified binary search algorithm
	
	if(high<low)
		return null;
	
	int mid = low+(high-low)/2;
	Node root = new Node(a[mid]); // call Node constructor
	root.left= createTree(a, low, mid-1); // recursive call
	root.right = createTree(a, mid+1, high); // recursive call
	
    return root;
	}
}
class Node{
int value;
Node left;
Node right;

	public Node(int data){
		this.value = data;
	}
}
/*
 * Analysis for each program, kth smallest and kth largest:
 * Time Complexity = O(n)
 * Space Complexity = O(1)
 */
