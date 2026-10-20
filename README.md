# Double-a-Number-Represented-as-a-Linked-List
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next
class Solution:
    def doubleIt(self, head: Optional[ListNode]) -> Optional[ListNode]:
        if head is None:
            return None
        r=[]
        temp=head
        while temp:
            r.append(temp.val)
            temp=temp.next
        c=0
        for i in range(len(r)-1,-1,-1):
            a=r[i]*2+c
            r[i]=a%10
            c=a//10
        if c:
            r.insert(0,c)
        d=ListNode(0)
        temp=d
        for i in r:
            temp.next=ListNode(i)
            temp=temp.next
        return d.next
