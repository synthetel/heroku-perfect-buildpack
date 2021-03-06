A Heroku Buildpack for Swift + Perfect
Packaged by Shao Miller <swiftcode@synthetel.com>
2016-03-22 13:25:42 UTC

This "Buildpack" makes dependencies available at the /app/.delta/ path.  These
include Swift and Perfect.

Your project must have the following file and directory structure:
  src/                : Contains your source code
  src/makefile        : Invoked by the Buildpack
  src/Package.perfect : Informs Buildpack about your Perfect project

Your project will have the following structure after building:
  PerfectLibraries/   : Modules for Perfect Server can go in here
  webroot/            : Files for Perfect Server stand-alone can go in here

Your project should have the following structure:
  Procfile            : This informs Heroku about processes to deploy

This Buildpack will move into your src/ directory, then invoke 'make', followed
by 'make install'.  See the following example Github project:

  https://github.com/PerfectlySoft/Perfect-Heroku-Buildpack-Example
