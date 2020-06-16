---
published: false
---
Go ahead and step into the kitchen. 
What do you see? 
Plates, bowls, containers and snacks and so many more delicious delicacies. 
Look closely.
You may also see something like this.
![1.PNG]({{site.baseurl}}/_posts/1.PNG)

Recognize those Plates on top of each other? 
This is precisely where the concept of Stack came from. 

Think about the things you can do with such a pile of plates.

You can either put a new plate on top or remove the top plate.

If you want the plate at the bottom, you have to first remove all the plates on top.
Such an arrangement is called Last In First Out - the last item that was placed is the first item to go out.

## Programming Jargons of Stack
In programming terms, putting an item on top of the stack is called "push" and removing an item is called "pop"

A stack is an object or more specifically an abstract data structure(ADT) that allows the following operations:

Push: Add an element to the top of a stack
Pop: Remove an element from the top of a stack
IsEmpty: Check if the stack is empty
IsFull: Check if the stack is full
Peek: Get the value of the top element without removing it.

Also needless to say, the topmost element is called the top()

We can implement stacks by using concrete data types called Array  and/or Linked Lists. They are linear data structures. The difference between them has to do with memory allocation.

![2.PNG]({{site.baseurl}}/_posts/2.PNG)


-Push(x)
-Pop()
-top()
-getMin()
Our main contender here will be the getMin() Operation.
Now, Storing the overall minimum sounds like a good idea. But once we pop an element, how do we find the minimum again in O(1) time?

Let’s look at this example
![3.PNG]({{site.baseurl}}/_posts/3.PNG)

Top points to 3

Our minima here is 3.

But if we pop 3, our minima shifts to 5.

If we pop 5, our minima should be 8.

How do we go about performing this in real time?

What we can do is:


We can duplicate this stack and have another stack called Stack B that looks exactly the same except.
![3.PNG]({{site.baseurl}}/_posts/3.PNG)
Whenever you insert an element in the new stack, you insert the new minimum from the previous stack A.

Therefore, Initially you will insert 19 as it is the only element, and then compare 8 and 19,
8 is the minimum therefore Stack B should have 8 as the second element

Now the third element is 23, compare the three elements, 8 is the minimum, hence 8 is inserted in Stack B again. 

SImilarly, 5 and 3 are inserted. 

So, now you can see that the second stack is telling us the current minimum number in the stack A in O(1) time.
Top of Stack B points to the current minimum element in Stack A.

So, By using this tradeoff of Space and time, we actually used more space but we were able to solve the entire problem in O(1) time.

The code implementation using C++ is given below:
![5.PNG]({{site.baseurl}}/_posts/5.PNG)
![6.PNG]({{site.baseurl}}/_posts/6.PNG)

You can get the code <a href="https://github.com/Shreya869/get_min-Stack-in-O-1-/tree/master
" target="_top">here</a>

