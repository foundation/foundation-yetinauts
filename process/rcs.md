### Process for RCs

Tentative process for setting up RCs
  
* For the first RC of a release, A ZURBian runs through the RC checklist and verifies the framework looks ready to RC.
* Said ZURBian tags the RC using `git tag` using the naming structure `vmajor.minor.point-rc1`. 
* In the case of a point release, ZURBian also creates a branch for this release named `vmajor.minor.point`.  This will allow for further forward progress on develop without destabilizing the release branch.
* In the case of a minor release, ZURBian will create a new branch for the next minor release that feature development can be targeted towards.
* Upon tagging, RC should be pushed to github as a 'pre-release' output.
* Publish an rc prerelease npm package (see http://carrot.is/coding/npm_prerelease)
* At this point, we should distribute a QA document and distribute QA tasks across Yetinauts.  Example QA document from 6.2.1: [here](https://docs.google.com/spreadsheets/d/1AeM1tcNltZGU0JiHlsw2rUb8ck-d8gHDVxGND2k3WLQ/edit?usp=sharing)
* We will attempt to turn around QA testing within about a week.  In that timeframe, we'll assess if there are any blocking bugs, with functional regressions being definitely blocking, and visual regressions considered on a case by case basis.
* We should also identify issues that were fixed during this release and ping their creators to test the RC.
 
## RC Prerelease Checklist
- Are there any deprecation warnings that need to be removed for this release?
- Does the current release build properly?
- .. ?
