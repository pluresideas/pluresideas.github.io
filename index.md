### How to speed up merge request code reviews?

When I create a merge request, I always go through the resulting change list in GitLab to verify one more time that all the changes are intentional. Sometimes during this process I find small things that I prefer to address right away. 

One of my merge request code reviews was delayed because I fixed a typo and some code documentation after I created this merge request. The team did not know when to start code reviews because I was still making changes which caused the delay. 

The solution is simple. In my next merge request, I approached the merge request from a perspective of a reviewer. I created an unresolved comment, made an update to the code base, and closed the original comment. Now, what I did was transparent to the team, and it should cause no delays. 

I would encourage reviewers to communicate with authors of merge requests using GitLab comments. The advantage is that there is a record of these communication available to anyone participating. 
