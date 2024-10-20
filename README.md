# Queue-Implementation

Aim:
To study and implement Queue implementation using array. menu options - i) Insert ii) Delete iii) Display iv) exit

Theory:
A queue is a linear data structure that follows the First In, First Out (FIFO) principle, meaning that the first element added is the first one to be removed.

Basic Operations:
Enqueue: Adds an element to the rear of the queue.
Dequeue: Removes and returns the element from the front of the queue.
Peek/Front: Returns the element at the front without removing it.
isEmpty: Checks whether the queue is empty.
isFull: Checks whether the queue is full (in the case of array implementation).
Queue Using Array:
Fixed Size: In the array implementation, the size of the queue is fixed, and a maximum size (capacity) must be predefined.
Index Tracking: Two pointers are used, front (points to the element at the front of the queue) and rear (points to the last element inserted).
Initially, both front and rear are set to -1.
As elements are enqueued, rear is incremented.
As elements are dequeued, front is incremented.

![377522234-d7554e1d-9187-483a-ae80-6d71f7f2954e](https://github.com/user-attachments/assets/77357d92-bb01-4805-beaa-2a650baf18b5)

Circular Queue: To optimize space in an array-based queue, the circular queue concept is often implemented, where the rear pointer wraps around to the front of the array once it reaches the end. This avoids unused spaces that occur in the standard queue when elements are dequeued.

![377522908-e715d118-3850-4061-bd36-c62320860e1d](https://github.com/user-attachments/assets/2687a35f-d0c1-4331-b89b-ff14a03ea488)

Program:
Algorithm:
Define Class Queue:

Attributes: rear (tracks the rear of the queue), front (tracks the front of the queue), and ar[] (array to store queue elements).
Initialize rear and front to -1 (empty queue) and set ar[0] to 0 in the constructor.
Enqueue Operation:

Check if rear has reached the maximum size (size+1), indicating that the queue is full.
If full, print "Queue is full."
If empty (front == -1), set both front and rear to 0, then insert the element at ar[0].
Otherwise, increment rear and insert the element at ar[rear].
Dequeue Operation:

Check if the queue is empty (front == -1 or front == rear + 1).
If empty, print "Queue is empty" and return ERROR.
Otherwise, return the element at ar[front] and increment front.
Display (disp) Operation:

Check if the queue is empty (front == -1 or front == rear + 1).
If empty, print "Queue is empty."
Otherwise, traverse the queue from front to rear and print each element.
Main Function:

Create an object of the Queue class.
Enqueue elements (4, 8, and 3) into the queue.
Display the queue elements using disp().
Dequeue the front element and display it.
Display the remaining elements in the queue.
Code:
//Priti
//23070123103
#include<iostream>
using namespace std;
#define size 5
#define ERROR -9999
class Queue
{
    int rear,front,ar[size];
    public:
    Queue()
    {
        rear=-1;
        front=-1;
        ar[0]=0;
    }
    void enqueue(int);
    int dequeue();
    void disp();
};
void Queue::enqueue(int num)
{
    if(rear==(size+1))
    {
        cout<<"Queue is full"<<endl;
    }
    else{
        if(front==-1)
        {
            ar[++front]=num;
            rear++;
        }
        else{
            ar[++rear]=num;
        }
    }
}
int Queue::dequeue()
{
    if(front==-1 || front==(rear+1)){
        cout<<"Queue is empty"<<endl;
        return ERROR;
    }
    else {
        int val=ar[front++];
        return val;
    }
}
void Queue::disp(){
    if(front==-1 || front==(rear+1)){
        cout<<"Queue is empty"<<endl;
    }
    else{
        int i= front;
        while(i!=(rear+1)){
            cout<<ar[i];
            i++;
        }
    }
}
int main()
{
    Queue q1;
    q1.enqueue(4);
     q1.enqueue(8);
      q1.enqueue(3);
      q1.disp();
      int val= q1.dequeue();
      cout<<endl<<"Deleted element: "<<val<<endl;
      q1.disp();
}
Output:

![Screenshot 2024-10-20 200135](https://github.com/user-attachments/assets/e83fc32c-058a-44d6-8f83-be3fec276387)

Conclusion:
We learnt about Stack and it's implementation using arrays in C++.



