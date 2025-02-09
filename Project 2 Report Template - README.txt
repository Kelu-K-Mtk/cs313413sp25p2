COMP 313/413 Project 2 Report Template

TestList.java and TestIterator.java

	TODO also try with a LinkedList - does it make any difference?

		ANS: > ArrayList in both cases is slightly slower to finish building (about .5 of a second slower). 
		     > This could be because ArrayList needs to resize its array as elements are added whereas LinkedList just adds a node. 

TestList.java

	testRemoveObject()

		list.remove(5); // what does this method do?

			ANS: > This removes the element at index 5 (in the given list, this is 77)

		list.remove(Integer.valueOf(5)); // what does this one do?

			ANS: > This removes the first instance of the number/value 5

TestIterator.java

	testRemove()

		i.remove(); // what happens if you use list.remove(77)?

		ANS: > Causes a runtime error (ConcurrentModificationException) as this tries to make modify the list while iterating.
		     > It removes first appearance of 77 from the list while i.remove() only removes last element

TestPerformance.java

	State how many times the tests were executed for each SIZE (10, 100, 1000 and 10000)
	to get the running time in milliseconds and how the test running times were recorded.
	These are examples of SIZEs you might choose, you can choose others if you wish.
	
	ANS: > Ran tests for each size 7 times using the code below to record the running times
	     
		public void testLinkedListAddRemove() {
   			long start = System.nanoTime();
    			for (var r = 0; r < REPS; r++) {
      				linkedList.add(0, 77);
      				linkedList.remove(0);
    			}

    			long end = System.nanoTime();
    			long runTime = (end - start)/1000000;
    			System.out.println(runTime + "ms");
  			}
	    > Repeated this for each method.
	

	SIZE 10
				 #1     #2     #3     #4    #5      #6 	   #7... (as many tests as you ran)
        testArrayListAddRemove:  13ms | 12ms | 7ms  | 10ms | 10ms | 9ms  | 8ms
        testLinkedListAddRemove: 20ms | 17ms | 21ms | 19ms | 23ms | 20ms | 17ms
	testArrayListAccess:     9ms  | 9ms  | 9ms  | 9ms  | 10ms | 8ms  | 10ms
        testLinkedListAccess:    288ms|	267ms| 267ms| 282ms| 292ms| 285ms| 281ms

	SIZE 100
				 #1     #2     #3     #4    #5      #6 	   #7... (as many tests as you ran)
        testArrayListAddRemove:  10ms | 10ms | 9ms  | 8ms  | 10ms | 9ms  | 9ms
        testLinkedListAddRemove: 19ms | 19ms | 21ms | 21ms | 23ms | 20ms | 20ms
	testArrayListAccess:     20ms | 20ms | 17ms | 19ms | 10ms | 18ms | 18ms
        testLinkedListAccess:    270ms|	285ms| 271ms| 277ms| 292ms| 287ms| 287ms

	SIZE 1000
				 #1     #2     #3     #4    #5      #6 	   #7... (as many tests as you ran)
        testArrayListAddRemove:  8ms  | 8ms  | 8ms  | 10ms | 15ms | 12ms | 9ms
        testLinkedListAddRemove: 20ms | 18ms | 18ms | 21ms | 21ms | 22ms | 20ms
	testArrayListAccess:     251ms| 258ms| 253ms| 252ms| 269ms| 294ms| 273ms
        testLinkedListAccess:    341ms|	380ms| 369ms| 369ms| 373ms| 391ms| 391ms

	SIZE 10000
				 #1      #2       #3     #4      #5      #6 	 #7... (as many tests as you ran)
        testArrayListAddRemove:  13ms  | 13ms  | 8ms   | 10ms  | 13ms  | 14ms  | 7ms
        testLinkedListAddRemove: 21ms  | 27ms  | 21ms  | 19ms  | 23ms  | 23ms  | 21ms
	testArrayListAccess:     5406ms| 3777ms| 5092ms| 3915ms| 4744ms| 4090ms| 5230ms
        testLinkedListAccess:    1325ms| 1378ms| 1324ms| 1204ms| 1341ms| 1295ms| 1342ms
	
	listAccess - which type of List is better to use, and why?

		ANS: > ArrayList is better for listAccess because it is able to retrieve elements faster
		     > This could be because it is an array structure

	listAddRemove - which type of List is better to use, and why?

		ANS: > LinkedList is better for listAddRemove because it is able to handle adding/removing elements more efficiently
