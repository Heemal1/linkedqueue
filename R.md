#include <stdio.h>
#include<stdlib.h>
  struct Node *f=NULL;
  struct Node * r=NULL;
struct Node{
    int data;
    struct Node * next;
};
void traversal(){
    struct Node * p=f;
    printf("elements are \n");
    while(p!=NULL){
    printf("%d\n",p->data);
    p=p->next;
}}
void enqueue(int val){
    struct Node * n=(struct Node *)malloc(sizeof(struct Node));
   
    if(n==NULL){
        printf("queue is full");
    }
    else{
         n->data=val;
         n->next=NULL;
        if(f==NULL){ f=r=n;
        }
        else{
            r->next=n;
            r=n;
        }
    }
    }
void dequeue(){
    if(f==NULL || r==NULL){
        printf("empty ");
        
    }
    else{
    struct Node * p =f ;
    f=f->next;
    printf("removed %d",p->data);
    free(p);
    
}}
int main() {

   enqueue(23);
   enqueue(34);
     dequeue();
     dequeue();
     dequeue();
   traversal(f);
  

    return 0;
}
