Introduction
This guide is aimed to help you better understand how to better deal with deployments in your development workflow and provide some best practices for deployments. Sometimes a bad production deployment can ruin all the effort you invested in a development process. Having a solid deployment workflow can become one of the greatest advantages of your team.

The Workflow
Deployments should be treated as part of a development workflow, not as an afterthought. The development workflow process will usually include at least the environment: Development, Staging and Production. In this case it will look like this.

Developers work on bugs and features in separate branches. Really minor updates can be committed directly to the stable development branch.
Once features are implemented, they are merged into the staging branch and deployed to the Staging environment for quality assurance and testing.
After testing is complete, feature branches are merged into the master branch.
On the release date, the master branch is merged into stable and then deployed to the Production environment.
Let’s take a closer look at each environment to see what are the most efficient way to deploy each one of them.

Development Environment
We noticed that some teams have Development environments set up with automatic deployments on every commit or push. While this gives developers a small advantage of not installing the site or the application on their computers to perform testing locally, it also wastes a lot of time. Every tiny change must be committed, pushed, deployed, and only then it can be verified. If the change was made by mistake, a developer will have to revert it, push it, then redeploy.

Testing on a local computer removes the need to commit, push and deploy completely. Every change can be verified locally first, then, once it’s more or less stable, it can be pushed to a Staging environment for proper quality assurance testing.

It's not recommended using deployments for rapidly changing development environments. Running your software locally is the best choice for that sort of testing.
Staging Environment
Once the features are implemented and considered fairly stable, they get merged into the staging branch and then automatically deployed to the Staging environment. This is when quality assurance kicks in: testers go to staging servers and verify that the code works as intended.

It is very handy to have a separate branch called staging to represent your staging environment. It will allow developers to deploy multiple branches to the same server simultaneously, simply by merging everything that needs to be deployed to the staging branch. It will also help testers understand what exactly is on staging servers at the moment, just by looking inside the staging branch.

-It's recommended to deploy to the staging environment automatically on every commit or push.

Production Environment
Once the feature is implemented and tested, it can be deployed to production. If the feature was implemented in a separate branch, it should be merged into a stable development branch first. The branches should be deleted after they are merged to avoid confusion between team members.

The next step is to make a diff between the production and development branches to take a quick look at the code that will be deployed to production. This gives you one last chance to spot something that’s not ready or not intended for production. Stuff like debugger breakpoints, verbose logging or incomplete features.

Once the diff review is finished, you can merge the development branch into production and then initialize a deployment of the production branch to your Production environment by hand. Specify a meaningful message for your deployment so that your team knows exactly what you deployed.

Make sure to only merge development branch into production when you actually plan to deploy. Don’t merge anything into production in advance. Merging on time will make files in your production branch match files on your actual production servers and will help everyone better understand the state of your production environment.

- Recommended always deploying major releases to production at a scheduled time, of which the whole team is aware of. Find the time when your application is least active and use that time to roll out updates. This may sound obvious, but make sure that it’s not too late, because someone needs to be around after the deployment for at least a few hours to monitor the application and make sure the deployment went fine. Urgent production fixes can be deployed at any time.

After deployment finishes make sure to verify it. It is best to check all the features or fixes that you deployed to make sure they work properly in production. It is a big win if your deployment tool can send an email to all team members with a summary of changes after every deployment. This helps team members to understand what exactly went live and how to communicate it to customers.

Your deployment to production is now complete.
