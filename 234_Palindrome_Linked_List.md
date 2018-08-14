## Follow up:
Could you do it in O(n) time and O(1) space?

## Solution 1: beat	99.77%	1ms
The goal is to split the list in two halves, and compare the first half with the second half. 
Reverse the first half, and walk from the middle to two ends. 
1. Count	length	of	List
2. Reverse	the	first	part
3. Compare	tow parts from	mid
4. mid	=	mid	or	mid.next	according	to	the	length	is	odd	or	even

## Conclusion 1: time	O(N),	space	O(1)

## Solution	2	:
1.	need	to	find	how	to	compare	the	start	and	end	point	at	Linkedlist
2.	reverse	the	second	parts	of	list	which	is	after	mid	point
3.	compare	two	lists
				
				
## Conclusion	2:	
two	difficulities
1)	need	to	very	clear	how	to	splite	a	linkedlist
a)	if	fast	=	slow	=	head,
1-2-3,	slow(mid)	slow	=	2	fast	=	3
1-2-3-1,	slow(mid)	is	at	3,	fast	=	null
after	break	and	reverse	
1->2->1->null		=>	1->2;	1<-2<-1
1->2->2->1->null	=>	1->2;	2<-2<-1

b)	if	fast	=	head.next,
1-2-3,	slow(mid)	slow	=	2	,	fast	=	null
1-2-3-4,	slow(mid)	slow	=	2, fast	=	4			
1-2-3-4-5-6,	slow	=	3	fast	=	6

for	this	question,	there	is	no	different	for	a)	and	b)
since	1-2-2-1	after	break	and	reverse,	1->2		1<-2<-2<-1

总结： time	O(N),	space	O(1)
要懂快慢指针， slow	=	head,	fast	=	head	 slow	=	head,	fast	=	head.next	

## Solution	3	( an excellent problem to study recursive) beat	37.62%	run	3ms	
need	to	understand	recursive.	Need	to	discuss	with	the	interviewee,	if	the	recursive	
space	is	considered as	space	cost.
1. Recursively	call	with	(head,	head)		
2. the first head,	pass	head.next	with	each	call
3. the second parameter	head,	the same, but when the first param reaches return, return head and return value returns start.next
一个是从上自下go next，一个是自下往上go next, 比较value的不同
4. 有两个点. 
a. compare method只能return ListNode, 所以用null代表false
b. 当start.next == null. 并不是return null而是return start, 因为return代表false
