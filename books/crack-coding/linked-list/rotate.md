# Rotate

## LC61. Rotate List

[lc61](https://leetcode.com/problems/rotate-list/)

{%tabs%}
{%tab title="Go"%}
```go
/**
 * Definition for singly-linked list.
 * type ListNode struct {
 *     Val int
 *     Next *ListNode
 * }
 */
func rotateRight(head *ListNode, k int) *ListNode {
    if head == nil {
        return head
    }
    p, l := head, 1
    for p.Next != nil {
        p = p.Next
        l++
    }
    p.Next = head
    k %= l
    for i := 0; i < l - k; i++ {
        p = p.Next
    }

    ret := p.Next
    p.Next = nil
    return ret
}
```
{%endtab%}
{%endtabs%}