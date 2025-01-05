## Implement a Singly Linked List

``` bash
class MyLinkedList(object):

    def __init__(self):
        self.head = None
        self.tail = None
        self.size = 0

        
    def get(self, index):
        """
        :type index: int
        :rtype: int
        """
        if index >= self.size:
            return -1
        else:
            head = self.head
            prev = None
            for i in range(0,index):
                prev = head
                head = head.next
        
        return head.val

    def addAtHead(self, val):
        """
        :type val: int
        :rtype: None
        """
        if self.head:
            node = Node(val)
            node.next = self.head
            self.head = node
        else:
            self.head = Node(val)
            self.tail = self.head

        self.size += 1
        

    def addAtTail(self, val):
        """
        :type val: int
        :rtype: None
        """
        if self.tail:
            node = Node(val)
            self.tail.next = node
            self.tail = node
        else:
            self.tail = Node(val)
            self.head = self.tail

        self.size += 1

    def addAtIndex(self, index, val):
        """
        :type index: int
        :type val: int
        :rtype: None
        """
        if index == 0:
            node = Node(val)
            node.next = self.head
            self.head = node
        elif self.size == index:
            node = Node(val)
            self.tail.next = node
            self.tail = node
        elif index >= self.size:
            return
        else: 
            node = Node(val) 
            head = self.head
            prev = None
            for i in range(0,index):
                prev = head
                head = head.next
            if prev: 
                prev.next = node
                node.next = head
            else:
                self.size -= 1
        self.size += 1

    def deleteAtIndex(self, index):
        """
        :type index: int
        :rtype: None
        """
        if index >= self.size:
            return
        elif index == 0:
            self.head = self.head.next
        else:
            head = self.head
            for i in range(0,index):
                prev = head
                head = head.next
        
            prev.next = head.next
            if prev.next is None:
                self.tail = prev
            
        
        self.size -= 1
```

## Reverse Linked list

```bash
if not head:
    return head
curr = head
prev = None
next = curr.next

while curr and next:
    curr.next = prev
    prev = curr

    curr = next
    next = curr.next
```

## Merge two sorted lists
```bash
if list1 and list2:
    head = None
    root = None
    if list1.val > list2.val:
        head = list2
        list2 = list2.next
    else:
        head = list1
        list1 = list1.next
    root = head
    while list1 and list2:
        if list1.val > list2.val:
            head.next = list2
            head = head.next
            list2 = list2.next
        else:
            head.next = list1
            head = head.next
            list1 = list1.next
    
    if list1:
        head.next = list1
    
    if list2:
        head.next = list2

    return root
else:
    if list1:
        return list1
    elif list2:
        return list2
    else:
        return None

```

curr.next = prev
return curr
```
