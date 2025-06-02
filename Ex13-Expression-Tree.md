# Ex13 Expression Tree
## DATE:
## AIM:
To write a C function to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order ,Pre-order and Post-order traversal.

## Algorithm
```
1. Read the postfix expression as input.
2.For each symbol in the postfix expression:
      i)If it’s an operand, create a node and push it onto a stack.
      ii)If it’s an operator, pop two nodes, create a new node with the operator, and set the popped nodes as its children.
3.After processing all characters, the expression tree root will be at the top of the stack.
4.Traverse and print the tree in in-order, pre-order, and post-order forms.
5.Display each traversal on a new line.   
```
## Program:
```
/*
Program to construct an Expression Tree for the given Postfix Expression and display the output in the format of In-order ,Pre-order and Post-order traversal.
Developed by: Sharmitha V
RegisterNumber: 212223110048
#include <stdio.h>
#include<stdlib.h>
struct n {
   char d;
   struct n *l;
   struct n *r;
};
char pf[50];
int top = -1;
struct n *a[50];
int r(char inputch) {
   if (inputch == '+' || inputch == '-' || inputch == '*' || inputch== '/')
      return (-1);
   else if (inputch >= 'A' || inputch <= 'Z')
      return (1);
   else if (inputch >= 'a' || inputch <= 'z')
      return (1);
   else
      return (-100);
}
void push(struct n *tree) {
   top++;
   a[top] = tree;
}
struct n *pop() {
   top--;
   return (a[top + 1]);
}
void construct_expression_tree(char *suffix) {
   char s;
   struct n *newl, *p1, *p2;
   int flag;
   s = suffix[0];
   for (int i = 1; s != 0; i++) {
      flag = r(s);
      if (flag == 1) {
         newl=(struct n *)malloc(1*sizeof(struct n));

         newl->d = s;
         newl->l = NULL;
         newl->r = NULL;
         push(newl);
      } else {
         p1 = pop();
         p2 = pop();
         newl=(struct n *)malloc(1*sizeof(struct n));
         newl->d = s;
         newl->l = p2;
         newl->r = p1;
         push(newl);
      }
      s = suffix[i];
   }
}
void preOrder(struct n *tree) {
    if (tree==NULL){
        return;
    }
    printf("%c",tree->d);
    preOrder(tree->l);
    preOrder(tree->r);
}
void inOrder(struct n *tree) {
    if(tree==NULL){
        return;
    }
    inOrder(tree->l);
    printf("%c",tree->d);
    inOrder(tree->r);
}
void postOrder(struct n *tree) {
    if(tree==NULL){
        return;
    }
    postOrder(tree->l);
    postOrder(tree->r);
    printf("%c",tree->d);
   
}
int main() {
 
   scanf("%s",pf);
   construct_expression_tree(pf);
  // printf("\nIn-Order Traversal : ");
   inOrder(a[0]);
   printf("\n");
   //printf("\nPre-Order Traversal : ");
   preOrder(a[0]);
   printf("\n");
   //printf("\nPost-Order Traversal : ");
   postOrder(a[0]);
   return 0;
}

*/
```

## Output:

![image](https://github.com/user-attachments/assets/53118e64-5ca7-4c34-ab69-bd651aab6959)



## Result:
Thus, the C program to display the Expression Tree in the format of In-order ,Pre-order and Post-order traversal.
