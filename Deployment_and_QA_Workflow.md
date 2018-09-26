Deployment and QA Workflow
Motivation
The main outcome of following this approach is so that as a team we can deploy, well tested, working features on a daily basis. It's also so that we can get much more involvement from the client or a representative of the client. Read on!

Story creation and start
Project Manager adds a new story with as much detail as possible ('As a..., I want..., So that...')
Project Manager will include in the story the text to be used for the RSpec specification.
Project Manager needs to keep these stories as small as possible. This ensures that we will be able to deploy as often as possible.
Developer estimates the story
Developer clicks 'Start'
Developer branches from stable branch always naming the branch starting with the story id e.g. 150350058_some_new_fancy_feature where 150350058 is the Pivotal Tracker Story ID of the feature being developed. This is so that a comment can be added to the story automatically after deployment to Staging to notify QA.
Story completion, pull request, code review
Developer submits a Pull request to the Master branch (this should automatically trigger a message in the teams Slack channel to notify the team that there is code ready to review)
Code is reviewed by your peers having a constructive discussion together about it. Who performs the code review? Anyone on the team! When can I perform the code review on someones pull request? we have two time slots in the day: 9am and 1.30pm which will be completely reserved for code review. At both of these times of the day, if there is any pull request that needs to be reviewed then it must be done at the this time!
Ask the PM to review the specification text so that it can be re-written if necessary.
During Code Review please follow our best practices.
Eventually the code review passes and we move on to the next step!
Deployment to Staging
Developer merges the feature into the Master branch (which will trigger an auto deploy to the Staging environment).
NOTE: if there are merge conflicts then always resolve these conflicts by merging your branch INTO master and keeping both sets of code. It's recommended to do this on your own development machine rather than the Github UI.
When the deployment is complete the Developer clicks 'Finish'
QA Testing Process in Staging
Notify QA with a comment in the story like '@panha here are the links: + adds screen shots from Staging if necessary'). The QA team will test feature based on the specification written for the feature.
If feature FAILS QA then:
QA will comment back to the developer if feature is not working / not delivered as expected. Some reasons are: not following 'Design Principals', does not follow expected requirements, breaks or crashes app etc.
Developer will continue to make changes on their feature branch, commit code changes to github and submit a new Pull Request for code review.
If the feature PASSES QA then:
Writes comment '@damon QA passed' if passed QA
PM will write comments back to the developer to either make further changes or to deploy the feature to Production.
Decide whether to add a feature flag or not!
At this point the feature has gone through lots of testing but still needs more - in Production!
Developer can decide at this point if the feature needs a feature flag or not. It really depends on the size of the feature and the risk of breaking in Production.
So take this time to decide and talk with the PM about it too if you like.
Feature Branch Deployment to Production and Performance Testing
Developer will merge stable INTO their feature branch
Developer then deploys their feature branch to Production
Feature branch deployments to Production at this point are LOCKED
Developer checks that the Production server is still running as expected, that response times are good, error count is stable etc,etc. This should take about 10 or 15 minutes.
IF any issues seem to be happening now (like error count shooting up rapidly) then simply deploy the stable branch back to Production and figure out what is happening using logs and further testing in Staging.
Developer then merges their branch into the stable branch (which should trigger an auto deployment of stable to Production).
Developer then checks the Production server again and keeps a close eye on performance, errors and so on.
Developer clicks 'Delivered' in Pivotal Tracker.
Feature testing in Production (optionally behind a feature flags)
Feature is now deployed into Production and is optionally behind a feature flag
Project Manager will ask the Developer for the test specification report from CodeShip specific to the feature being deployed and will add these details to the story. This is basically the feature spec output.
Project Manager can notify client and/or client representative to test the feature directly in Production
Anyone at Rotati can also test the feature
Specific users of the clients team can also be given access to test the feature
Once the feature is approved by the client the story can be finally Accepted (and the feature flags removed if there are any - see below)! Yay!
Project manager will click 'Accepted' on the story in Pivotal Tracker.
Removing feature flags from Production (only for features where feature flags have been applied)
Developer will branch from stable branch
Developer will remove the feature flags for this feature
Developer will perform a 'branch deploy' to production
Developer will perform some performance and error checking as mentioned above
Developer will merge their branch into stable, thus triggering a deployment of stable to Production which essentially will make the new feature live to all (since the feature flag has been removed).
Developer will merge stable into master to update the Staging environment.
Developer will delete their feature branch :)
Application Demos
Demo the application to the entire team every 2 week so that everyone is on the same page
Demos allow for cross team collaboration, ideas and knowledge sharing
During the demo remember to update the ScoreCard in Stemware
Keeping the client involved and the team happy!
Do not leave too many stories in a 'Delivered' state (that is pending 'Accepted / Rejected'). To avoid this we need to ensure that the customer checks the feature as soon as possible while its behind the feature flag.

If we delay too long for the client to give feedback then we risk the following issues:

It reduces the Velocity (in Pivotal Tracker),
Increases the likelihood that the app is not being developed in the correct / expected way
Increases stress levels of the project manager to have to review too many stories
Increases the chances of stories being rejected and then having to halt progress on moving forward in the backlog
Will increase the estimates being off by a few days (maybe weeks)
Reduces the motivation of the team since they like to see their work accepted as soon as possible
It means the client is less engaged with the product development
Keeping the client involved ensures that we keep momentum up and expectations met!

References
Pivotal Tracker States
Pivotal Tracker Story Point Estimates
Git Branching Strategy


