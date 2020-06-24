### How to speed up merge request code reviews?

When I create a merge request, I always go through the resulting change list in GitLab to verify one more time that all the changes are intentional. Sometimes during this process I find small things that I prefer to address right away. 

One of my merge request code reviews was delayed because I fixed a typo and some code documentation after I created this merge request. The team did not know when to start code reviews because I was still making changes which caused the delay. 

The solution is simple. For my next merge request, I approached the merge request from a perspective of a reviewer. I created an unresolved comment, made an update to the code base, and closed the original comment. Now, what I did was transparent to the team, and it should cause no delays. 

I would encourage reviewers to communicate with authors of merge requests using GitLab comments. The advantage is that there is a record of these communication available to anyone participating. 

### How to distribute code reivew workload?
Developers love coding but not so much doing code reviews, naturally. On my project developers who wrote the code are responsible for finding reviewers.

How do I fairly distribute this kind of work? How do I ensure that the code base knowledge spreads among the developers evenly?

The solution is simple. I started using a Google spreadsheet where each reviewer on my team gets from 0.1 to 1 point for each completed review based on my estimation of the effort. The total number of points developers earn provides me with hits as to who the next reviewer should be.

|Developer|Total Earned|Completed Code Reviews Weight|	
|---------|------------|-----------------------------|
|James	|1.2	|1	|0.1	|0.1
|Mary	|1	|1		
|Patricia	|0.2	|0.1	|0.1	
|Robert	|0.5	|0.5		
|Jennifer	|0			
|Michael	|0.5	|0.5			
