# OmnifocusScripts
These are scripts I've written to automate Omnifocus and customize it to my needs.
![Screenshot](https://user-images.githubusercontent.com/3252725/27114790-b6f756fe-508b-11e7-85d4-b0bdf38c61b7.png)

## Toggl Integrations
The **Start Toggl Task** and **Complete Toggl Task** integrations are a pair of scripts that can be run from within Omnifocus to start and stop Toggl time entries connected with the Omnifocus task selected. Both scripts require you to enter your Toggl API (found within your account preferences) on the first run. **Complete Toggl Task** also requires [jq](https://stedolan.github.io/jq/) to be installed on your system. This can be easily installed with `brew install jq`. 

**Start Toggl Task** uses the selected task in Omnifocus and starts a Toggl time entry. The Omnifocus task ID gets recorded as a tag in Toggl to enable completion of the task, and a second tag "omnifocus" gets added to allow reporting on all Omnifocus tasks tracked this way. This script will ask what Toggl project you want to associate with your Omnifocus project (using all workspaces in Toggl) and then remembers this choice in a plist file.

**Complete Toggl Task** looks for the active Toggl time entry, and if it has an "of_" tag, then it finds that OmniFocus task and marks it complete. It also updates the estimated minutes in Omnifocus with the duration from Toggl. Finally, it removes the "of_" tag from the time entry.

## Other Omnifocus Scripts
The **Revise Time** script sets the estimated minutes field of the selected item(s) to the sum of estimated minutes for the tasks it contains.

## To-dos:
- Confirm that Toggl tags are getting removed correctly.
- [Workflow to adapt](https://www.macstories.net/ios/workflow-update-brings-ability-to-interact-with-any-web-api/)
