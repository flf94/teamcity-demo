# TeamCity Demo

Keep in mind:

* Try to minimize duplication (e.g. by using templates)
* Find the stuff that differs between builds and make it a parameter
* Try to organize things such that it is easy to get an overview

1. Clone the project to somewhere you have write access
1. Create a new project, attach the VCS and `compile` the project
1. Harvest artifacts produced by the compilation
1. Check out the `early-artifacts` task and use that as an alternative
   implementation of the last step
1. Create a build config to run tests (using the artifacts)
1. Split the test run into `test` (unit tests) and `integation-test`
1. Split `integration-test` by category
1. Run the `browser` integration test category on a build agent that has Chrome
   installed - How would you try to find a matching agent?
1. If all tests are successful, `deploy` the app
1. Add a build tab to display the deployment log
1. Add a project tab showing the last successful deployment log
1. What happens if you break unit or integration tests? (See `run-me` for docs)
1. Set up the build such that it's not possible to remove tests without breaking
   the build (See `run-me` for docs)
1. Generate the version number on the agent (`version`) and reuse the version
   for deployment
1. Extend the build to be able to run feature branches
1. Create a separate deployment step to production that only runs when `master`
   has been updated
