Certainly! Here's a markdown file for the given code:

```markdown
# Delete Middle Node

## Problem Statement

Given a singly-linked list, implement a function `deleteMiddle` to delete the middle node of the list. If the list has an even number of nodes, delete the second middle node.

## Approach

The given code implements the deletion of the middle node in a singly-linked list. It follows the following steps:

1. It checks if the head of the linked list is `NULL`. If so, it returns `NULL` since there are no nodes to delete.
2. It initializes two pointers `i` and `j` to traverse the linked list.
3. It counts the number of nodes in the linked list by iterating over the list using the pointer `i`.
   - Inside the loop, it increments the `size` variable for each node encountered.
4. It sets the pointer `i` back to the head of the linked list.
5. It initializes a variable `x` to 0 to keep track of the current node position.
6. It traverses the linked list again using the pointer `i` until reaching the middle node.
   - Inside the loop, it updates the pointer `j` to keep track of the previous node.
   - It also checks if `i->next` is `NULL` to handle cases where the list has an even number of nodes. If `i->next` is `NULL`, it means the list has an even number of nodes, and the second middle node should be deleted. In such cases, it sets `j` to `NULL` and returns `NULL` since there is no middle node to delete.
   - It moves `i` to the next node and increments `x` to keep track of the current position.
7. Once the middle node is found, it updates the `next` pointer of the previous node (`j`) to skip the middle node and point directly to the node after it.
8. Finally, it returns the head of the modified linked list.

## Complexity Analysis

Let's assume n is the number of nodes in the linked list.

- Time Complexity: The code performs two traversals over the linked list. The first traversal counts the number of nodes, which takes O(n) time. The second traversal finds the middle node, which takes O(n) time in the worst case. Therefore, the overall time complexity is O(n).
- Space Complexity: The code uses a constant amount of extra space. It does not allocate any additional dynamic memory based on the input size. Hence, the space complexity is O(1).

## Code Implementation
```

```cpp
class Solution {
public:
    ListNode* deleteMiddle(ListNode* head) {
        if (head == NULL)
            return NULL;

        int size = 0;
        int x = 0;

        for (ListNode* i = head; i != NULL; i = i->next)
            size++;

        ListNode* i;
        ListNode* j;
        i = head;
        while (x < size) {
            j = i;
            if (i->next == NULL) {
                j = NULL;
                return NULL;
            }
            i = i->next;
            x++;
        }
        j->next = i->next;
        return head;
    }
};
```

This code takes the head of a singly-linked list as input and deletes the middle node of the list. If the list has an even number of nodes, it deletes the second middle node. It returns the head of the modified linked list.
