# Ex8 Detection of Cycle and Finding the Starting Node in a Linked List
## DATE:21/11/25
## AIM:
To write a program that detects a cycle in a linked list and returns the node where the cycle begins.
If there is no cycle, the program should return null without modifying the linked list.
## Algorithm
1. 
2. 
3. 
4.  
5.   

## Program:
```
/*
program that detects a cycle in a linked list and returns the node where the cycle begins.
If there is no cycle, the program should return null without modifying the linked list.
Developed by: MADHULEHA K
RegisterNumber: 212224060140  
*/

class Node {
    int data;
    Node next;
    Node(int data) {
        this.data = data;
        this.next = null;
    }
}

public class DetectCycleLinkedList {
    static Node detectCycle(Node head) {
        Node slow = head, fast = head;
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
            if (slow == fast) {
                Node entry = head;
                while (entry != slow) {
                    entry = entry.next;
                    slow = slow.next;
                }
                return entry;
            }
        }
        return null;
    }

    public static void main(String[] args) {
        Node head = new Node(1);
        head.next = new Node(2);
        head.next.next = new Node(3);
        head.next.next.next = new Node(4);
        head.next.next.next.next = new Node(5);

        head.next.next.next.next.next = head.next.next; // Create cycle

        Node cycleStart = detectCycle(head);
        if (cycleStart != null)
            System.out.println("Cycle detected at node with value: " + cycleStart.data);
        else
            System.out.println("No cycle detected.");
    }
}
```

## Output:
<img width="1292" height="397" alt="image" src="https://github.com/user-attachments/assets/7dd0e3e2-e923-4fc5-b08c-f4ed6471926f" />



## Result:
The program successfully detects whether a cycle exists in the linked list.
If a cycle is present, it correctly identifies and returns the node where the cycle begins.
