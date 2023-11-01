# Quiz questions

This is only a "quiz" in the loosest sense that it's asking questions whose
answers will be part of your grade. Please use *any resources you want*, as
long as you list those resources (e.g. peers, websites, etc.)

## Navigating logs

1. What is the SHA for the last commit made by Prof. Xanda on the branch
xanda_0000_movie_processing?
(For this and future questions, the first 5 characters is plenty - neither
Git nor I need the whole SHA.)

9b257

2. What is the SHA for the last commit associated with line 9 of this file?

a0774

3. What did line 12 of this file say in commit d1d83?

I should really finish writing this

4. What changed between commit e474c and 82045?

Changes a variable and type casted

## Predicting merges

Assume at the start of each of these three questions that your
branch for switching to a top-10 list was called `top_ten`
and your branch generalizing to any number of movies was called `top_N`.
Predict the behavior of these three possible operations - you don't
have to provide a full `diff` but you should describe at a high level
what changes would happen.

These questions are supposed to be separate paths, not cumulative;
for example, you should *not* assume that the operations of 5 were run
before 6. When testing outcomes later in the lab, you should make sure to
revert back to the state of the branch before you started these questions.

5. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git merge top_N
```

We would first switch to the test branch, then we would merge the changes made to the top_N branch into the test branch. Any commits unique to the top_N branch would be added to the history of the test branch as well. We would also need to resolve any merge conflicts.

6. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout top_ten
git merge test
```

We would switch to the top_ten branch. We would then merge the changes from the test branch into the top_ten branch. Any commits that are unique to the test branch will be added to the history of the top_ten branch as well. We will also need to resolve any merge conflicts (similar to q 5)

7. What do you think would happen if you ran the following commands?
What branches would change, and how?
```
git checkout test
git rebase top_ten
git rebase top_N
```

We would first switch to the test branch. The we would try to reapply the commits from the test branch into the top_ten branch. This would earase and re do the history of the test branch to make it seem like all the changes were made on the last commit of the top_ten branch. Finally we would attmpt to reapply the newly rebased commits of the test branch to the top_N branch. This will also rewrite the history and made the test branch changes look like they were all made during the last commit to the top_N branch. We would have to resolve conflicts manually.  
