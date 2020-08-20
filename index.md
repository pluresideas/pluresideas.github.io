### How to speed up merge request code reviews?

When I create a merge request, I always go through the resulting change list in GitLab to verify one more time that all the changes are intentional. Sometimes during this process I find small things that I prefer to address right away. 

One of my merge request code reviews was delayed because I fixed a typo and some code documentation after I created this merge request. The team did not know when to start code reviews because I was still making changes which caused the delay. 

The solution was simple. For my next merge request, I approached the merge request from a perspective of a reviewer. I created an unresolved comment, made an update to the code base, and closed the original comment. Now, what I did was transparent to the team and it should cause no delays. 

I would encourage reviewers to communicate with authors of merge requests using GitLab comments. The advantage is that there is a record of these communications available to anyone participating. 

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

Inspecting the Issue Links sections, examining dependencies is a good way of identifying gaps. Linking user stories by using the Issue Links sections also prevents starting working on user stories when dependencies are not yet satisfied. My suggestion is to link user stories as soon as possible, when they are created.

### How to architect solutions?

Solution architecture may have the biggest impact on the projects’ success, requires significant experience so it is important to do it right. Not all developers acting as architects have the required experience.

I suggest that companies develop a process requiring developers acting as architects or participating in the process to submit the work to be reviewed by their company architect.

### How to build a system with integration points successfully?

When building a system which integrates with other systems it is important to identify any impacts or gaps early on. Identifying impacts to the integration interfaces which are not in the control of the implementation team is especially important. The required impacts need to be added to a project plan, feasibility evaluated, and the implementation could have impact on the system being built. 

It can be very tempting to start building new services, the system infrastructure, pipelines, executing performance tests, evaluating tools and libraries. Teams with low confidence would likely start here. 

Confident teams know they can build any system. They have tools to mimic the work of the system and to interact with the integration interfaces without writing any code. They would examine the requested features and attempt to fulfill these features by interacting with the integration interfaces mimicking the work of the system.

These exercises would not only confirm feasibility, identify any impacts, but would also help teams with understanding of the system they need to integrate with. Once the interaction with the integration interfaces is know, the architecture work can start.

With this approach there is a better chance of an earlier success, less rework, resulting in cost savings which is a win for everyone. 

### How to define units of work?

Units of work definitions always specify what needs to be done. Knowing ‘why’ is just as important. It helps developers with understanding of the work and guides the implementation.

Stories missing the ‘why’ are often debated during planning, implementation, and even during the implementation review. Some of the stories are found as not needed because the ‘why’ statement was not captured or understood.

Of course a good definition of units of work needs other parts as well but I would urge the teams to start with using ‘why’. This [article](https://medium.com/@SFWebDigital/the-5-key-components-of-an-agile-user-story-6586ea63e1db)
 captures all the important parts. 

Which methodology teams use, agile, waterfall or something else is unimportant; the success of the implementation stars with a good understanding of the work needed.

### Code review - How to retain knowledge gained during code reviews?

I received this code review comment:

"14, 24, and 32 or so have ‘section’ as id names. These are examples as mentioned that do not accurately reflect the implied html. Just something I consider a 'best practice' to avoid."

The reviewer inspected an html, matching style sheet, and was not satisfied with the css selector names. He spent some time thinking what the names should (not) be however this knowledge did not get captured in his code review comment.

My suggestion would be for the reviewers to document their suggestions. Suggestions add clarity to the code review comments.
