#include <stdio.h>
#include<stdlib.h>
struct queue
{
  int size,f,r;
  int *arr;
};
void enqueue(struct queue *q,int value)
{
  if((q->r+1)%q->size==q->f)
  {
    printf("queue is full\n");
  }
  else
  {
    q->r=(q->r+1)%q->size;
    q->arr[q->r]=value;
    printf("element added successfully\n");
  }
}
void dequeue(struct queue *q)
{
  if(q->f==q->r)
  {
    printf("stack is empty\n");
  }
  else
  { int value;
    q->f=(q->f+1)%q->size;
    value=q->arr[q->f]; 
    printf("element deleted successfully: %d\n",value);
  }
}

int main(void) 
{
struct queue q;
q.arr=(int *)malloc(sizeof(int));
q.size=500;
q.f=0;
q.r=0;

enqueue(&q,10);
enqueue(&q,20);
enqueue(&q,30);
enqueue(&q,40);
enqueue(&q,50);
enqueue(&q,60);
enqueue(&q,70);
printf("elements present in the array:\n");
for(int i=1;i<=q.r;i++)
{
  printf("%d\n",q.arr[i]);
}
dequeue(&q);
dequeue(&q);
dequeue(&q);

}
