# Inorder_Tree_Traversal_java
package treedatastructure;
import java.util.*;
public class TREEDATASTRUCTURE {
    public static void main(String[] args) {
        // TODO code application logic here
        TreeNode node1=new TreeNode(1);
        TreeNode node2=new TreeNode(2);
        TreeNode node3=new TreeNode(3,node1,node2);
        TreeNode node4=new TreeNode(4);
        TreeNode node5=new TreeNode(5);
        TreeNode node6=new TreeNode(6,node4,node5);
        TreeNode root=new TreeNode(10,node3,node6);
        List<Integer> li=inorder(root);
        System.out.print(li);
        
    }
    public static List<Integer> inorder(TreeNode root){
        List<Integer> result=new ArrayList<>();
        inorderHelper(root,result);
        return result;
    }
    public static void inorderHelper(TreeNode root,List<Integer> result){
         if(root==null){
             return;
         }
         inorderHelper(root.left,result);
         result.add(root.data);
         inorderHelper(root.right,result);
    }
}
class TreeNode{
    int data;
    TreeNode left;
    TreeNode right;
    public TreeNode(){
        this.data=0;
        this.left=null;
        this.right=null;
    }
    public TreeNode(int d){
        this.data=d;
        this.left=null;
        this.right=null;
    }
    public TreeNode(int d,TreeNode left,TreeNode right){
        this.data=d;
        this.left=left;
        this.right=right;
    }
}
