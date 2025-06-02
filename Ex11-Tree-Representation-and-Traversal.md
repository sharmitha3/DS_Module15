# Ex11 Tree Representation and Traversal
## DATE:
## AIM:
To write a C function to perform post order traversal of a binary tree.

## Algorithm
```
1. If the current node is NULL, return (base case).
2.Recursively call post-order traversal on the left child.
3.Recursively call post-order traversal on the right child.
4.After both children are processed, print the value of the current node.
5.This ensures nodes are visited in Left → Right → Root order.
```
## Program:
```
/*
Program to perform post order traversal of a binary tree.
Developed by: Sharmitha V
RegisterNumber: 212223110048
/*struct node
{
int value;
struct node *left_child, *right_child;
};*/
void display_postorder(struct node *root_node) {
    if(root_node==NULL){
        return;
    }
    display_postorder(root_node->left_child);
    display_postorder(root_node->right_child);
    printf("%d\n",root_node->value);
}
*/
```

## Output:

![image](https://github.com/user-attachments/assets/8da0ebc3-1c6d-40c3-9e5c-a2aa05dc2adb)


## Result:
Thus, the function to perform post order traversal of a binary tree is implemented successfully
