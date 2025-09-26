[[COURSES/BIE-GIT/LECTURE 1|LECTURE 1]]
## SOFTWARE DEVELOPMENT TECHNOLOGIES


BIE-GIT guarantor pulcpetr@fit.cvut.cz - Petr Pulc
Git lecturer & corporate consultant oburkrob@fit.cvut.cz

Versioning with BIE-PA1 will reward 50 points. Alternatively, a semestral project will do the same.
Short videos available at https://online.fit.cvut.cz/zaznam/archiv/

Basic Philosophy
=====================

File: "A named sequence of bytes stored on a data medium."

Versioning: A way to keep different versions of a file.

Versioning Control System: A smart way to keep different versions of a file.


Repository: An archive of work on a single project.

Commit: A unit of work stored in a repository

Branch: A logical grouping of several commits, typically solving a single task. May have special functions (main, integration, etc.)

While programming, one can see what they actually added and changed. If they iterated to a non-working version, they can easily go back and try a different path. If after releasing/deploying a new version of the application, one found that something is not working as expected, they can easily restore the previous version (even at the component level).

Multiple people can work on the same code. Changes from authors do not have to be independent, they need to be able to merge them. They may use branches for common work to our advantage. They need to have some means of informing each other about their work.

Merge/Pull Request: A request to include a set of changes (branch) into the main branch of the project.

Code Review: "Analysis" of changes by more experienced colleagues, or discussion of suitability / details of the chosen solution.

Continuous Integration: A method of continuous qualitative and functional testing.

The program needs to be compiled and packages, artifacts, containers, etc. need to be created. Often, several independent applications or even machines are involved in the distribution. All steps are automatable, but they need a consistent reference to the data source.

Continuous Deployment: A method of continuously publishing new versions.


Git is simple, yet powerful. If everything looks like a file, dictionary or other project it can be the hammer for the nail. On the other hand, due to the amount of control given to the user, it may result in g