# Lab Report 5

## Part 1

__Brandon Khor__

Help! I am trying to do step 3 for practice skill demo 4, but I have no clue what to fix! Here is a screenshot of the symptom:

![Image](error5.png)

I understand that the bugs are in the `ListExamples.java` file, but I have no clue where! The failure-inducing inputs are definitely in the `TestListExamples.java` file, but I am so sure that my expected values should match my actual!

__Andy (My glorious TA)__

Hmm. Very interesting! So first, let's look back at our symptom. What do you notice? Now, let's open up the `ListExamples.java` file with `vim` so we can look for bugs.

__Brandon Khor__

I see that for the `filter` method, the filter of accepting strings that contain the character `a` is working, but it is in a different order than my test case!

__Andy (My glorious TA)__

That's weird indeed! Well we know that the error doesn't lie with the process of filtering, but rather the ordering. Maybe look for a line in the code that is responsible for that?

__Brandon Khor__

Hmm, let me see... OH MY DAYS!!! IT'S PREPENDING INSTEAD OF APPENDING! That's why the order was so wack! If I go to line 15 and change `result(0, s)` to `result(s)`, then the issue should be fixed! Andy, you're a genius!

__Andy (My glorious TA)__

Oh stop flattering me! Anyways, don't celebrate too early. We still have another bug to address! Do you remember the test case that failed?

__Brandon Khor__

I remember it has to deal with the merge method, but the error message isn't as helpful! It just says that the test timed out! What am I supposed to do with that information!

__Andy (My glorious TA)__

Never fear, Andy is here! Think about common reasons why a program would time out. Why won't the program end?

__Brandon Khor__

Hmm. I think I got it! The program won't end if there is an infinite loop! And look here, there are 3 `while` loops in the `merge` method! Surely the bug must lie within those. And will you look at that! On line 43, `index2` isn't incremented at all, so the statement while loop will never stop! We can fix this by changing `index1` to `index2`. What would I do without you Andy?!

__Andy (My glorious TA)__

Hold your horses now, make sure those were the correct changes by running that trusty `bash` script again!

__Brandon Khor__

Alright, here goes nothing!

