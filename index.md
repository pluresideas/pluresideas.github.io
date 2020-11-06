### How to speed up merge request code reviews?

When I create a merge request, I always go through the resulting change list in GitLab to verify one more time that all the changes are intentional. Sometimes during this process I find small things that I prefer to address right away. 

One of my merge request code reviews was delayed because I fixed a typo and some code documentation after I created this merge request. The team did not know when to start code reviews because I was still making changes which caused the delay. 

The solution was simple. For my next merge request, I approached the merge request from a perspective of a reviewer. I created an unresolved comment, made an update to the code base, and closed the original comment. Now, what I did was transparent to the team and it should cause no delays. 

I would encourage reviewers to communicate with authors of merge requests using GitLab comments. The advantage is that there is a record of these communications available to anyone participating. 

### How to distribute code reivew workload?
Developers love coding but not so much doing code reviews, naturally. On my project, developers who wrote the code are responsible for finding reviewers.

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

During the last user stories refinement meeting I glanced over the Issue Links section and pointed out that I can't find a prerequisite user story. The scrum master swiftly created it and linked it to the user story we were refining. I was surprised that couple of developers quickly adopted this process and applied it during the same meeting. Using the Issue Links section was a new concept for the team.

Inspecting the Issue Links sections, examining dependencies is a good way of identifying gaps. Linking user stories by using the Issue Links sections also prevents starting working on user stories when dependencies are not yet satisfied.

### How to architect solutions?

Solution architecture may have the biggest impact on the projects' success, requires significant experience so it is important to do it right. Not all developers acting as architects have the required experience.

I suggest that companies develop a process requiring developers acting as architects or participating in the process to submit the work to be reviewed by their company architect.

### How to build a system with integration points successfully?

When building a system which integrates with other systems it is important to identify any impacts or gaps early on. Identifying impacts to the integration interfaces which are not in the control of the implementation team is especially important. The required impacts need to be added to a project plan, feasibility evaluated, and the implementation could have impact on the system being built. 

It can be very tempting to start building new services, the system infrastructure, pipelines, executing performance tests, evaluating tools, and libraries. Teams with low confidence would likely start somewhere here. 

Confident teams know they can build any system. They have tools to mimic the work of the system and to interact with the integration interfaces without writing any code. They would examine the requested features and attempt to fulfill these features by interacting with the integration interfaces mimicking the work of the system.

These exercises would not only confirm feasibility, identify any impacts, but would also help teams with understanding of the system they need to integrate with. Once the interaction with the integration interfaces is know, the architecture work can start.

With this approach there is a better chance of an earlier success, less rework, resulting in cost savings which is a win for everyone. 

### How to define units of work?

Units of work definitions always specify what needs to be done. Knowing 'why' is just as important. It helps developers with understanding of the work and guides the implementation.

Stories missing the 'why' are often debated during planning, implementation, and even during the implementation review. Some of the stories are found as not needed because the 'why' statement was not captured or understood.

Of course a good definition of units of work needs other parts as well but I would urge the teams to start with using 'why'. This [article](https://medium.com/@SFWebDigital/the-5-key-components-of-an-agile-user-story-6586ea63e1db)
 captures all the important parts. 

Which methodology teams use, agile, waterfall or something else is unimportant; the success of the implementation stars with a good understanding of the work needed.

### Code review - How to retain knowledge gained during code reviews?

I received this code review comment:

"14, 24, and 32 or so have 'section' as id names. These are examples as mentioned that do not accurately reflect the implied html. Just something I consider a 'best practice' to avoid."

The reviewer inspected an html, matching style sheet, and was not satisfied with the css selector names. He spent some time thinking what the names should (not) be however this knowledge did not get captured in his code review comment.

My suggestion would be for the reviewers to document their suggestions. Suggestions add clarity to the code review comments.

### Get a team's buy-in first

We all love recognition from our clients. Sometimes we rush with presenting our plans, research, architecture, or other work without getting the team's buy-in. It is too late for the team to ask questions when the work is already being presented to a client.

I would advise presenting the work first to your team only in a safe environment. Be prepared to defend your work. Respond to comments and questions just like you would respond to code review comments.


### How to not to ask questions? 

I recently reviewed a pipeline code where a developer added a `lint` stage to a Jenkins file. I noticed `docker run` was used to run a docker image and then `lint` was executed from a shell of the docker container.

I questioned the developer the order of the pipeline steps. I would expect that first the code would be checkout out, lint, built, and tests executed and only then when all these steps succeeded a docker image should be created.

The developer copied and pasted someone else's code without understanding how it works, was not able to speak about it, and was going to ask other developers whether my concern was a valid or not. I could see from my conversation with him that he does not understand the fundamentals of my concern. I wanted him to understand my concern so that my concern would become his concern as the <del>author</del> of the code, that he would be able to carry a discussion with other developers. Clearly he was not ready for such discussion as I failed to articulate my concern to him clearly. 

I think repeating someone's question without the ability to defend and talk about it, is not as helpful as one might think.

### Discourage asking for help privately

Today, I was asked to help with getting our older React project running after two developers were unable to do so.

The additional components were a NodeJS authentication proxy, OAuth 2.0 authentication server, and finally the API using AWS CLI. 

One of the issues I encountered was the `401 unauthenticated` error. I opened up the project’s README.  In the `Common Pitfalls` section, that I wrote a while back, I found the solution: the application client ID and secret were invalid. This was an easy fix. 

The next issue was the `403 forbidden` error. I checked my account role and noticed that my account was missing the proper role. 

I asked the other developer whether he is experiencing the same `403 forbidden` error. He said that he experience the `401 unauthenticated` error.

If the developer used the team’s Slack channel to report the error, I would have been able to quickly point him in the right direction. Since he did not do this, three developers were tied up in the same effort trying to get the project running. 

Teams should be discouraged from asking for help privately.

### Mocking without using a library

We oftentimes reach out to popular mocking libraries when writing unit tests. Alternatively we could use features of the programing language to achieve the same goal.

In this simplified example I use the classic NestJS controller and service pattern:

```
import { Controller, Get } from '@nestjs/common';
import { ProductTypeService } from './product-type.service';

@Controller('/product-type')
export class ProductTypeController {
  constructor(private readonly productTypesService: ProductTypeService) {}

  @Get('/list')
  productTypeList(): string[] {
    return this.productTypesService.productTypeList();
  }
}
```

The service class implements an interface. This interface is used later for mocking of the service.
```
import { Injectable } from '@nestjs/common';

export interface ProductTypeServiceInterface {
  productTypeList(): string[];
}

@Injectable()
export class ProductTypeService implements ProductTypeServiceInterface {
  productTypeList(): string[] {
    return ['Convenience', 'Shopping', 'Speciality', 'Unsought'];
  }
}
```

When mocking of the service is not required writing a unit test is quite simple with composing the object being tested.
```
import { ProductTypeController } from './product-type-controller';

describe('ProductTypeController', () => {
  describe('ProductTypeService', () => {
    describe('productTypeList()', () => {
      it('should return a list of product types', () => {
        const productTypeListValues = ['Convenience', 'Shopping', 'Speciality', 'Unsought'];
        const productTypeList = new ProductTypeController(new ProductTypeService()).productTypeList();
        expect(productTypeList).toEqual(productTypeListValues);
      });
    });
  });
});
```

When mocking of the service is required, I construct a mock of the service by using the already mentioned service interface.
```
import { ProductTypeController } from './product-type-controller';
import { ProductTypeService, ProductTypeServiceInterface } from './product-type.service';

describe('ProductTypeController', () => {
  describe('ProductTypeService', () => {
    describe('productTypeList()', () => {
      it('should return a list of product types', () => {
        const productTypeListValues = ['A', 'B', 'C'];
        const productTypeService = <ProductTypeServiceInterface>{
          productTypeList: () => productTypeListValues,
        };
        const productTypeList = new ProductTypeController(productTypeService).productTypeList();
        expect(productTypeList).toEqual(productTypeListValues);
      });
    });
  });
});
```

What are the advantages of this approach?

This approach enables building up valuable programming skills in the given programming language and framework.
Here in this example I mimicked [@Injectable](https://docs.nestjs.com/providers) by composing the [object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects) being tested, and created the service mock by implementing an [interface](https://www.typescriptlang.org/docs/handbook/interfaces.html).

In addition, understanding and writing of these tests does not require knowledge of a particular mocking library.

### Code exercises for interviews

Last week I reviewed a coding exercise submitted by a senior full-stack developer. He used Angular for frontend and NestJS for backend.

Given the assignment, I expected the backend service module to be simple. However, it had 262 lines of code. I noticed several issues like not understanding a difference between `map()` and `forEach()`, unnecessary initialization of local variables to `null`, not making private class fields private, unused class fields, module imports, and many other issues. 

The most concerning issues was that the code did not work right. The developer did not realize that this `@Injectable()` service is a singleton. The file read cash’s implemented in this service incorrectly exposed an internal error state to all callers of the backend API. Once the error state was set by a first caller, it was set for all callers of the API.

The assignment did not ask for implementation of the file read cash so the developer went beyond what was actually needed. This made the service class much larger, harder to read, and see other issues. Correct refactoring of this service module or using a cash library would be the right thing to do. However the easiest would be not to implement the cash at all.

I would prefer less but quality code, documenting any potential shortcomings or possible improvements in the project’s `README` file. Such work would be rated much higher.

### Notification for changes to project’s dependencies

I investigated options for notifications when project’s dependencies change so that we know when to initiate a process for approving these changes. The approval process is outside of the scope of code reviews. 

I added a new job to the project’s GitLab CI pipeline file, `.gitlab-ci.yml`. This job only executes when `package.json` or `package-lock.json` change as part of a `git push` to GitLab. The notification is implemented as a call to a Slack’s Webhook.
The Slack's Webhook URL should not be shared or committed to the code base. For production, use GitHub's custom environment variables for storing the URL.

```
# Detects changes to package.json and package-lock.json
Detected Dependency Change:
  stage: Detected Dependency Change
  only:
    changes:
      - package.json
      - package-lock.json
  variables:
    SLACK_WEBHOOK_URL: https://hooks.slack.com/services/slack_token
    SLACK_WEBHOOK_HEADERS: "Content-type: application/json"
    DEPENDENCY_CHANGE_MSG: "Detected changes to package.json or package-lock.json"
  script: |
    echo $DEPENDENCY_CHANGE_MSG
    echo "Installing cURL CLI tool:"
    apk --no-cache add curl
    echo "Involking Slack Webhook notification:"
    curl -X POST -H $SLACK_WEBHOOK_HEADERS --data "{'text':'$DEPENDENCY_CHANGE_MSG | $CI_PROJECT_NAME |
    $CI_COMMIT_BRANCH | $CI_PROJECT_URL | $CI_JOB_URL | $CI_MERGE_REQUEST_PROJECT_URL |
    $CI_MERGE_REQUEST_SOURCE_PROJECT_URL | $CI_PIPELINE_URL | $GITLAB_USER_NAME'}"  $SLACK_WEBHOOK_URL
```

The resulting Slack notification contains useful information about the project name, branch and clickable links to the project's GitLab page, job, pipeline, etc.
