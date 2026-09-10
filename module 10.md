EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

void insert(struct Node **head, char data)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
    }
}

void search(struct Node *head, char key)
{
    int position = 1;

    while (head != NULL)
    {
        if (head->data == key)
        {
            printf("Element %c found at position %d\n", key, position);
            return;
        }

        head = head->next;
        position++;
    }

    printf("Element %c not found in the linked list\n", key);
}

void display(struct Node *head)
{
    while (head != NULL)
    {
        printf("%c ", head->data);
        head = head->next;
    }

    printf("\n");
}

int main()
{
    struct Node *head = NULL;
    char key;

    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');
    insert(&head, 'D');
    insert(&head, 'E');

    printf("Linked list elements:\n");
    display(head);

    printf("Enter the element to search: ");
    scanf(" %c", &key);

    search(head, key);

    return 0;
}
```
Output:
```
Linked list elements:
A B C D E
Enter the element to search: C
Element C found at position 3
```

Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    char data;
    struct Node *next;
};

void insert(struct Node **head, char data)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
    }
}

void display(struct Node *head)
{
    printf("Linked list elements:\n");

    while (head != NULL)
    {
        printf("%c ", head->data);
        head = head->next;
    }

    printf("\n");
}

int main()
{
    struct Node *head = NULL;
    char data;

    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');

    display(head);

    printf("Enter the character to insert: ");
    scanf(" %c", &data);

    insert(&head, data);

    printf("Linked list after insertion:\n");
    display(head);

    return 0;
}
```
Output:
```
Linked list elements:
A B C
Enter the character to insert: D
Linked list after insertion:
A B C D
```

Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

int main()
{
    struct Node *head = NULL;
    struct Node *second = NULL;
    struct Node *third = NULL;
    struct Node *temp;

    head = (struct Node *)malloc(sizeof(struct Node));
    second = (struct Node *)malloc(sizeof(struct Node));
    third = (struct Node *)malloc(sizeof(struct Node));

    head->data = 10;
    head->prev = NULL;
    head->next = second;

    second->data = 20;
    second->prev = head;
    second->next = third;

    third->data = 30;
    third->prev = second;
    third->next = NULL;

    temp = head;

    printf("Doubly linked list elements:\n");

    while (temp != NULL)
    {
        printf("%d ", temp->data);
        temp = temp->next;
    }

    printf("\n");

    free(head);
    free(second);
    free(third);

    return 0;
}
```
Output:
```
Doubly linked list elements:
10 20 30
```

Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *prev;
    struct Node *next;
};

void insert(struct Node **head, int value)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
        newNode->prev = temp;
    }
}

void display(struct Node *head)
{
    printf("Doubly linked list elements:\n");

    while (head != NULL)
    {
        printf("%d ", head->data);
        head = head->next;
    }

    printf("\n");
}

int main()
{
    struct Node *head = NULL;
    int value;

    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);

    printf("Before insertion:\n");
    display(head);

    printf("Enter the element to insert: ");
    scanf("%d", &value);

    insert(&head, value);

    printf("After insertion:\n");
    display(head);

    return 0;
}
```
Output:

```
Before insertion:
10 20 30
Enter the element to insert: 40
After insertion:
10 20 30 40
```

Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST


Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
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


Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node
{
    int data;
    struct Node *next;
};

void insert(struct Node **head, int data)
{
    struct Node *newNode;
    struct Node *temp;

    newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->next = NULL;

    if (*head == NULL)
    {
        *head = newNode;
    }
    else
    {
        temp = *head;

        while (temp->next != NULL)
        {
            temp = temp->next;
        }

        temp->next = newNode;
    }
}

void deleteElement(struct Node **head, int key)
{
    struct Node *current;
    struct Node *previous = NULL;

    if (*head == NULL)
    {
        printf("Linked list is empty\n");
        return;
    }

    current = *head;

    if (current->data == key)
    {
        *head = current->next;
        free(current);

        printf("Element %d deleted successfully\n", key);
        return;
    }

    while (current != NULL && current->data != key)
    {
        previous = current;
        current = current->next;
    }

    if (current == NULL)
    {
        printf("Element %d is not present in the list\n", key);
        return;
    }

    previous->next = current->next;
    free(current);

    printf("Element %d deleted successfully\n", key);
}

void display(struct Node *head)
{
    printf("Linked list elements:\n");

    while (head != NULL)
    {
        printf("%d ", head->data);
        head = head->next;
    }

    printf("\n");
}

int main()
{
    struct Node *head = NULL;
    int key;

    insert(&head, 10);
    insert(&head, 20);
    insert(&head, 30);
    insert(&head, 40);
    insert(&head, 50);

    printf("Linked list before deletion:\n");
    display(head);

    printf("Enter the element to delete: ");
    scanf("%d", &key);

    deleteElement(&head, key);

    printf("Linked list after deletion:\n");
    display(head);

    return 0;
}
```
Output:

```
Linked list before deletion:
10 20 30 40 50
Enter the element to delete: 30
Element 30 deleted successfully
Linked list after deletion:
10 20 40 50

```


Result:
Thus, the function that deletes a given element from a linked list is verified successfully.
