# EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
# Aim:
To write a C program to display stack elements using linked list.

# Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
# Program:
```
struct Node   
{  
float data;  
struct Node *next;  
}*head;  
void display()  
{  
    while(head!=NULL)
    {
        printf("%.2f\n",head->data);
        head=head->next;
    }
}
```

# Output:

<img width="655" height="658" alt="Screenshot 2025-08-12 161653" src="https://github.com/user-attachments/assets/2ced25ab-780f-4d8f-b9c1-3e6f208aab72" />

# Result:
Thus, the program to display stack elements using linked list is verified successfully. 



# EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
# Aim:
To write a C program to pop an element from the given stack using liked list.

# Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
# Program:
```
struct Node   
{  
float data;  
struct Node *next;  
}*head;  
void pop()  
{ 
    struct Node*temp;
    if(head==NULL)
    {
        printf("stack is empty");
    }
    else
    {
        temp=head;
        head=head->next;
        free(temp);
    }
}
```
# Output:


<img width="655" height="339" alt="Screenshot 2025-08-12 161722" src="https://github.com/user-attachments/assets/4b6f328a-3615-4d67-bdb9-a3f4caf60b3f" />


# Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
# EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
# Aim:
To write a C program to display queue elements using linked list.
# Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
# Program:

```
struct Node
{
   int data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void display()
{
    struct Node *temp;
    temp=front;
    if(rear==NULL)
    {
        printf("queue is empty");
    }
    else
    {
        while(temp!=NULL)
        {
            printf("%d\n",temp->data);
            temp=temp->next;
        }
    }
}
```
# Output:

<img width="596" height="534" alt="Screenshot 2025-08-12 161738" src="https://github.com/user-attachments/assets/2d85ee50-812e-4cbf-9ae0-eb55b9477fec" />

# Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
# EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

# Aim:
To write a C program to insert elements in queue using linked list

# Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
# Program:
```
struct Node
{
   char data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void enqueue(char data)
{
    struct Node *newnode;
    newnode=(struct Node*)malloc(sizeof(struct Node));
    newnode->data=data;
    newnode->next=NULL;
    if(front==NULL && rear==NULL)
    {
        front=rear=newnode;
    }
    else
    {
        rear->next=newnode;
        rear=newnode;
    }
}
```
# Output:


<img width="592" height="527" alt="Screenshot 2025-08-12 161748" src="https://github.com/user-attachments/assets/c05506cc-8afe-4246-a837-f06c8552c835" />

# Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



# EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


# Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

# Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

# Program:

```
struct Node
{
   char data;
   struct Node *next;
}*front=NULL,*rear=NULL;
void peek()
{
    printf("%c\n",front->data);
}
```

# Output:


<img width="531" height="666" alt="Screenshot 2025-08-12 161802" src="https://github.com/user-attachments/assets/78f3d540-80f3-4bda-9a8e-046a669c3532" />

# Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.
