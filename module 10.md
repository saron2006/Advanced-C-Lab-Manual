# EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
# Aim:
To write a C program to search a given element in the given linked list.

# Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
# Program:
```
struct Node{
    float data; 
    struct Node *next;
}*head;

void search(float data)
{
    struct Node *p;
    p=head;
    int i=1,x;
    while(p!=NULL)
    {
        if(p->data==data)
        {
            printf("item %.2f found at location %d", p->data, i);
            x=0;
        }
        i++;
        p=p->next;
    }
    if(x!=0)
    {
        printf("Item not found");
    }
}
```

# Output:
<img width="806" height="477" alt="Screenshot 2025-08-12 160758" src="https://github.com/user-attachments/assets/f4e8e1ce-7f1e-45ce-a5ad-e3ddee858c11" />

# Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
# EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
# Aim:
To write a C program to insert a node in a linked list.
# Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
# Program:
```
struct Node{
    int data; 
    struct Node *next;
}*head;
void insert(int data)
{
     struct Node *newnode;
     newnode= (struct Node *)malloc(sizeof(struct Node));
     newnode->data = data;
     newnode->next = NULL;
     if(head== NULL)
     {
         head = newnode;
     }
     else
     {
         struct Node *temp = head;
         while(temp->next !=NULL)
             temp= temp->next;
            
         temp->next = newnode;
     }
         
     
}
    
```
# Output:

<img width="807" height="689" alt="Screenshot 2025-08-12 160814" src="https://github.com/user-attachments/assets/5435fd6d-bc1b-4c15-b1a1-0d6e75488bcc" />

 
# Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
# EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
# Aim:
To write a C program to traverse a doubly linked list.

# Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
# Program:

```
struct Node
{
    struct Node *prev;
    struct Node *next;
    int data;
}*head;

void display()
{
    struct Node *ptr;
    ptr=head;
    while(ptr!=NULL)
    {
        printf("%d\n", ptr->data);
        ptr=ptr->next;
    }
    
}
```

# Output:

<img width="808" height="652" alt="Screenshot 2025-08-12 160826" src="https://github.com/user-attachments/assets/9b3a17f9-58f0-4627-ad7b-99fa5f82734c" />


# Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



# EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
# Aim:
To write a C program to insert an element in doubly linked list

# Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
# Program:

```
struct Node
{
    struct Node *prev;
    struct Node *next;
    char data;
}*head;

void insert(char data)
{
    struct Node *newnode, *t;
    newnode=(struct Node *)malloc(sizeof(struct Node));
    if(newnode == NULL)
    {
        newnode= head;
        return;
    }
    else{
        newnode->data = data;
        if(head==NULL)
        {
            newnode->next= NULL;
            newnode->prev=NULL;
            head= newnode;
        }
        else{
    t= head;
    while(t->next!=NULL)
    {
        t=t->next;
    }
    t->next= newnode;
    newnode->prev= t;
    newnode->next= NULL;
    }
    }
    
    
    
    
    
}
```

# Output:

<img width="808" height="640" alt="Screenshot 2025-08-12 160840" src="https://github.com/user-attachments/assets/4450fbf5-5c40-462d-9648-e9056c4ddaf5" />


# Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




# EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




# Aim:
To write a C function that deletes a given element from a linked list.
# Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


# Program:

```
struct Node{
    float data; 
    struct Node *next;
}*head;
void delete()
{
    struct  Node *p;
    if(head==NULL)
    {
        printf("List is empty");
    }
    else
    {
    p= head;
    head= head->next;
    free(p);
    printf("Node deleted from the begining ...\n");
    }
    
}
```

# Output:
<img width="804" height="658" alt="Screenshot 2025-08-12 160853" src="https://github.com/user-attachments/assets/b35394d8-a2aa-4da3-9612-350c6b4a915a" />


# Result:
Thus, the function that deletes a given element from a linked list is verified successfully.
