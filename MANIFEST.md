**product scope** To create a simple app that will take a picture of a body of text (usually from a physical book) and count the number of words. The user will use a simple finger drag gesture on their phone to select all the words they want to "count". This number is then displayed on the app.

**target user** teachers or students use the app to verify the number of words another student has counted (in a minute) - without having to manually count each word.

**architecture** I would like this to be a webapp that works seamlessly on phones, or alternatively a phone app that could be sideloaded (android to begin with). webapp would be easier to begin with.

**workflow** I would like edits proposed in patches. I would like to create a subagent for this project. subagent is "Code Reviewer and Scribe" role: “Code Reviewer & Scribe: periodically scan recent changes, spot issues, and keep docs up to date.​ "Code Reviewer & Scribe" Inputs: diffs since last run, test results, lint output, and current docs files. 