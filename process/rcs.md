### Process for RCs

Tentative process for setting up RCs
  
* For the first RC of a release, A ZURBian runs through the RC checklist and verifies the framework looks ready to RC.
* In the case of a point release, ZURBian also creates a branch for this release named `vmajor.minor.point`.  This will allow for further forward progress on develop without destabilizing the release branch.
* In the case of a minor release, ZURBian will create a new branch for the next minor release that feature development can be targeted towards.
* Build distribution with the updated rc version (npm run deploy:prep)
* Commit distribution and tag it with name `vmajor.minor.point-rc1`
* Upon tagging, RC should be pushed to github as a 'pre-release' output.  See below for structure of release notes.
* Publish an rc prerelease npm package (see http://carrot.is/coding/npm_prerelease)
* At this point, we should distribute a QA document and distribute QA tasks across Yetinauts.  Example QA document from 6.2.1: [here](https://docs.google.com/spreadsheets/d/1AeM1tcNltZGU0JiHlsw2rUb8ck-d8gHDVxGND2k3WLQ/edit?usp=sharing)
* We will attempt to turn around QA testing within about a week.  In that timeframe, we'll assess if there are any blocking bugs, with functional regressions being definitely blocking, and visual regressions considered on a case by case basis.
* We should also identify issues that were fixed during this release and ping their creators to test the RC.
 
## RC Prerelease Checklist
- Are there any deprecation warnings that need to be removed for this release?
- Does the current release build properly?
- .. ?


## Release Notes Structure

Release notes should start with an intro of the theme of the release, with any major highlights or key bugfixes, any breaking changes/migration questions, and settings variable updates.

Following we want a changelog that is granular at the level of PRs, broken up by component.  These should start with #, followed by brief description and callout to contributor.

At the end of the changelog, if there are templates updates, include those in a 'Templates' section.

Finally, a link to the entire commit history.
