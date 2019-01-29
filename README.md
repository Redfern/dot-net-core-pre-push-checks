# Dot Net Core Git Pre Push Checks

This is a git pre push script for dot net core to check your push isn't going to break the build and will pass all unit tests.

## What to do

You need to place this is your git repo folder in /.git/hooks/, this is a hidden folder so you will have to turn on "show hidden folders" or cd into the dir in terminal. E.g. cd /.git/hooks inside of your local repo folder.

All you should need to change is on line 32, "cd test", change this to to the root folder of your test project. e.g. cd test/MyTestProject.

## How to run

Everything is automated, and will run on every "git push" command. Git knows to look in the .git/hooks folder and as long as the file is named "pre-push" then all will work.

### Fails

If the pre-push fails, then you will get a red terminal message of:

1. Failed to build the project, please fix this and push again
2. Unit tests failed, please fix and push again

### Pass

If the pre-push all passes, then you will get a green terminal message of:

1. Pre push check passed!

Your push will also be pushed to your git repo.

## Issues

These are some things I have came across while running this pre-push.

1. If you haven't pulled the most recent changes from your repo, then the pre-push check will run but only at the end of the pre-push you will be told you need to "git pull" the latest changes before you can push.
2. If you are running your application in visual studio, you will need to stop it running before the pre-push can run.
