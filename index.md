### How to speed up merge request code reviews?

When I create a merge request, I always go through the resulting change list in GitLab to verify one more time that all the changes are intentional. Sometimes during this process I find small things that I prefer to address right away. 

One of my merge request code reviews was delayed because I fixed a typo and some code documentation after I created this merge request. The team did not know when to start code reviews because I was still making changes which caused the delay. 

The solution is simple. For my next merge request, I approached the merge request from a perspective of a reviewer. I created an unresolved comment, made an update to the code base, and closed the original comment. Now, what I did was transparent to the team, and it should cause no delays. 

I would encourage reviewers to communicate with authors of merge requests using GitLab comments. The advantage is that there is a record of these communication available to anyone participating. 

### How to distribute code reivew workload?
Developers love coding but not so much doing code reviews, naturally. On my project developers who wrote the code are responsible for finding reviewers.

How do I fairly distribute this kind of work? How do I ensure that the code base knowledge spreads among the developers evenly?

The solution is simple. I started using a Google spreadsheet where each reviewer on my team gets from 0.1 to 1 point for each completed review based on my estimation of the effort. The total number of points developers earn provides me with hits as to who the next reviewer should be.

<table>
    <thead>
        <tr>
            <th>Developer</th>
            <th>Total Earned</th>
            <th colspan="3">Completed Code Review Weight</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>James</td>
            <td>1.2</td>
            <td>1</td>
            <td>0.1</td>
            <td>0.1</td>
        </tr>
        <tr>
            <td>Mary</td>
            <td>1</td>
            <td>1</td>
            <td></td>
            <td></td>
        </tr>   
        <tr>
            <td>Robert</td>
            <td>0.5</td>
            <td>0.5</td>
            <td></td>
            <td></td>
        </tr>
        <tr>
            <td>Jenifer</td>
            <td>0</td>
            <td></td>
            <td></td>
            <td></td>
        </tr>      
        <tr>
            <td>Patricia</td>
            <td>0.2</td>
            <td>0.1</td>
            <td>0.1</td>
           <td></td>
        </tr>    
        <tr>
            <td>Michael</td>
            <td>0.5</td>
            <td>0.5</td>
            <td></td>
            <td></td>
        </tr>         
</tbody>
</table>

### How to identify project gaps?

During the last user stories refinement meeting I glanced over the Issue Links section and pointed out that I can’t find a prerequisite user story. The scrum master swiftly created it and linked it to the user story we were refining. I was surprised that couple of developers quickly adopted this process and applied it during the same meeting. Using the Issue Links section was a new concept for the team.

Inspecting the Issue Links sections, examining dependencies is a good way of identifying gaps. Linking user stories by using the Issue Links sections also prevents staring working on user stories when dependencies are not yet satisfied. My suggestion is to link user stories as soon as possible, when they are created.

### How to architect solutions?

Solution architecture may have the biggest impact on the projects’ success, requires significant experience so it is important to do it right. Not all developers acting as architects have the required experience.

I suggest that companies develop a process requiring developers acting as architects or participating in the process to submit the work to be reviewed by the company architect.
