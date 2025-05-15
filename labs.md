# Working with GitHub Copilot Workspace
## From concept to code using Gen AI
## Revision 1.5 - 05/15/25

**Versions of dialogs, buttons, etc. shown in screenshots may differ from current version of Copilot**

**Follow the startup instructions in the README.md file IF NOT ALREADY DONE!**

**NOTES:**
1. We will be working in the public GitHub.com as our backing repository, not a private instance.
2. You **must** be on a paid plan to use Workspace.
3. VPNs may interfere with the ability to run the codespace. It is recommended to not use a VPN if you run into problems.
</br></br></br>
   

**Lab 1 - A quick run-through of using Workspace**

**Purpose: In this lab, we’ll start to learn about Copilot Workspace and how it generates code based on the prompts we provide**

1. Open a browser session and go to this link [New Workspace Session](https://copilot-workspace.githubnext.com)
</br></br>
2. If you're not already signed in, you'll need to sign in with your GitHub userid and password.

![Sign-in needed](./images/ws1.png?raw=true "Sign-in needed")
</br></br>
3. You'll then need to authorize your GitHub account.

![Authorize](./images/ws2.png?raw=true "Authorize")
</br></br>

4. We're going to create a project from scratch, so click on the *Create new repository* link.

![Create new repository start](./images/ws3.png?raw=true "Create new repository start")
</br></br>

5. Let's give Workspace a goal to create a simple tic-tac-toe game. In the task area, enter the command below.

```
create a tic-tac-toe game
```
</br></br>

6. Now, let's cut straight to the implementation. Click on the *Generate plan* button below the dialog area and then select the *Generate Code* option.

![Generate code](./images/ws29.png?raw=true "Generate code")
</br></br>

7. This will run for a while to generate all the code for your project.
</br></br>

8. After this is done, we'll create a repository to put our code in. In the upper right of the main Workspace screen, click on the *Create repository* screen.
</br></br>

![Create repo](./images/ws30.png?raw=true "Create repo")

9. Clicking on this button opens a dialog with a suggested name for the repo and a place for a description. The dialog includes a button to click to automatically generate the description/commit message. Click on that. Afterwards, you will see a description for the changes (formatted as markdown).

![Generate description](./images/ws31.png?raw=true "Generate description")
</br></br>
![With description](./images/ws32.png?raw=true "With description")
</br></br>

10. After generating the description and clicking on the button, GitHub creates the repo and presents you with a dialog to *Open in GitHub* or *Start new session*. Click on *Open in GitHub*. Afterwards, you should see something like below. (Depending on what Workspae created, you may or may not a README.md file that is filled in.)
   
![New repository](./images/ws35.png?raw=true "New repository")
</br></br>

11. Before continuing, we need to make one more change to the new repo. It will initially be *Private*. To avoid any issues for the next step, let's make it *Public*. Click on the *Settings* tab at the top of the repo. Then scroll down on that page to the *Danger Zone* area. Click the button to *Change visibility* and follow the prompt to make the new repo *Public*.

![Repo settings](./images/ws33.png?raw=true "Repo settings")
</br></br>
![Changing visibility](./images/ws34.png?raw=true "Changing visibility")
</br></br>
   
12. From here, you can clone your repository down locally and then run it - usually by opening up/starting/browsing to the *index.html* file.

```
git clone <path to repo>
cd <repo>
open index.html
```

![Running the game](./images/ws8.png?raw=true "Running the game")

 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>


**Lab 2 - Utilizing Workspace Features**

**Purpose: In this lab, we’ll start using Workspace's formal process to create a more defined app**

1. Start back at the main [Workspace home page](https://copilot-workspace.githubnext.com). You should see your session from Lab 1 listed in the *Recent sessions* area. Click again on *Create new repository* to start a new session.

![Starting a new session](./images/ws36.png?raw=true "Starting a new session")
</br></br>

2. Let's start this session by adding a very specific definition to Workspace of what we want. We wouldn't have to be this specific at all, but this will help ensure we get more accuracy and consistency in the result. In the task area, copy and paste the following requirement.

```
Task:
  • Implement a browser-based Tic-Tac-Toe game playable by two users  
  • Render a 3×3 grid of clickable cells  
  • Alternate X and O marks on each click  
  • Detect and display when one player wins or when the game is a draw  
  • Provide a “Restart” button to reset the board  

Dependencies & Components:
  • UI framework: Flask
  • Programming Language: Python

Acceptance Criteria:
  • A 3×3 board appears on page load  
  • Clicking an empty cell places “X” then “O” on alternating turns  
  • When three in a row appear (horiz, vert, diag), show “Player X wins!” or “Player O wins!”  
  • If all cells fill without a winner, display “Draw”  
  • “Restart” button clears the board and resets turn order
  • All needed environments setup
  • All needed dependencies and components installed
 
```

![Detailed requirements](./images/ws9.png?raw=true "Detailed requirements")

</br></br>

3. Now, click the green *Brainstorm* button at the bottom to go to the initial *brainstorming/planning* page.

</br></br>

4. On the right will be a *Brainstorm* section showing different ideas and approaches you can have Workspace implement for you. These ideas can range from basic implementation approaches to suggested options and possible advanced features. You can scroll through the ones that are listed. 

![Brainstorm list](./images/ws77.png?raw=true "Brainstorm list")

</br></br>

5. Click on the *+ Add to task* button for the ones for *Basic Implementation* and *Enhanced user experience* (or ones close to that - the titles may vary). After adding those to the task list, you will see a checkmark indicator in the upper right indicating *Added to task*. You will also see the *Ideas from brainstorming* listed in the *Repository* section on the left.

![Updated list](./images/ws78.png?raw=true "Updated list")

</br></br>

6. At the bottom of the *Ideas* list will be a *Suggested questions* section with some other ideas from Copilot on areas to explore and/or validate. You can scroll down and click on a particular question to see what Copilot would propose for it. This will usually show a series of suggested implementation details relevant to the overall question.

![Suggested questions](./images/ws79.png?raw=true "Suggested questions")

</br></br>

7. Pick one if you want and click on the *+ Add to task* button to add it into the *Tasks* area as one of the *Ideas from brainstorming*. Ones regarding visual interactions/design around improving the user experience are usually fairly straightforward. Be careful of items that may really raise the complexity. If you select an item, it will show up as *Added to task* and in the *Ideas from brainstorming* again.

![Adding items from question](./images/ws80.png?raw=true "Adding items from question")

</br></br>

8. With our set of initial tasks defined, we're ready to proceed to generating the plan. On the left side of the dashboard, click the *Generate plan* button.

![Generating the plan](./images/ws81.png?raw=true "Generating the plan")

</br></br>

9. Copilot will process for a few moments and then add a *Plan* section on the left under the *Repository* area. You can scroll down to see this. This section lists out all the files it expects to create along with the main logic that will be implemented in each. At the bottom, it will also show any commands that need to be run separately to install dependencies, setup environments, etc.(You may or may not have those.) And, on the right will be a list of *Uncommitted changes*. At this point, this is the set of files to be implemented.

![Plan section](./images/ws82.png?raw=true "Plan section")

</br></br>

10. If we were implementing changes against an existing code base, we would see diffs here for existing files. Since we don't yet have any actual files, we just see the list and names.

</br></br>

11. On the left, next to the *Task* tab, will be a new *Files* tab. Click on that and you'll see the proposed list of files again. Expand the directories for *static/css* and click on the *styles.css* file (assuming it exists in the list). Then click on the new tab on the right for *styles.css*. Notice that the bar at the bottom will also have changed to indicate we are revising the css file.

![Planned files](./images/ws83.png?raw=true "Planned files")

</br></br>

12. Let's add an item for a *dark theme* to it. Click on the *+ Add item* link at the list bottom. Then type in "Style the background with a dark theme". You can close the dedicated tab for *styles.css* when done.

![Adding dark theme](./images/ws84.png?raw=true "Adding dark theme")

 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 3 - Implementation to Execution**

**Purpose: In this lab, we’ll see how to complete the code generation and run the example.**

1. Before we go further, if you don't have a section at the bottom of the plan to install Flask and create a *requirements.txt* file, let's set that up. (If you already have that, you can skip to step 4.) First, in the text area at the bottom, click on the icon to the left (probably a ? in a circle) and select the *Revise* mode.

![Change mode](./images/ws85.png?raw=true "Change mode")

</br></br>

2. With the *Revise* mode selected, enter the prompt into the text area: "Install Flask and create a requirements.txt file" and submit the prompt.

![Prompt to update](./images/ws86.png?raw=true "Prompt to update")

</br></br>

3. After a few moments, Workspace should add a new *requirements.txt* file to the list of files to be implemented. Scroll to the bottom off the plan and you should also see a *Commands* section with the terminal commands to install Flask and add it to the *requirements.txt* file.

![Updates to plan](./images/ws87.png?raw=true "Updates to plan")

</br></br>

4. Now that we have our plan in place, we can go ahead and have Workspace create the initial version of the files. At the bottom of the *Task/Plan* area (click back on *Task* if needed) is a button to *Implement selected files*. In the *Plan* area, make sure that all files are checked (check in the box). Then click on the *Implement selected files* button to have Copilot generate the selected files.

</br></br>

5. After the code generation completes, the *Files changed* section will show the proposed implementations. Scroll through and review the proposed changes. You also have an option to add additional features to a file by using the *+ Add item entry* in the file's section on the Plan.

![Proposed code](./images/ws88.png?raw=true "Proposed code")

</br></br>

6. Back on the left side, in the *Task/Plan* area, there should be a section at the bottom titled *Commands* that contains any terminal commands that need to be executed. If so, click on the *play* button next to the the command(s) to automatically open a terminal and execute the command(s). After running it will be checked off as completed in the task list.

![Run completed](./images/ws89.png?raw=true "Run completed")

</br></br>

7. In the top row of controls is a section of icons for starting other dev interfaces (marked in red in figure), including ones to open a dialog for commands and a terminal, one to open a GitHub Codespace, and one to open the code in VS Code. From running the commands in the plan, we'll already have a *Commands* tab open. Let's configure individual commands for Build, etc. Click on the downward arrow next to *Build* and then click on *Configure commands* at the bottom.

![Configure commands](./images/ws90.png?raw=true "Configure commands")

</br></br>

8. Workspace presents us with a screen where we can enter standard commands to build, test, and run our code.  You can input a command directly in the appropriate field or click on the light bulb icon at the end to have Copilot suggest a command. For our content as of now, we just need to be able to *Run* it. So, at the end of the *Run* area, click the light bulb icon. After spinning for a bit, Copilot should suggest something like the command below. If not, you can automatically type that in (or just omit the pip install since we've done that already). Afterwards, click on the *Save* button to save the changes.

```
pip install -r requirements.txt && python app.py
```

![Configure Run command](./images/ws91.png?raw=true "Configure Run command")

</br></br>

9. Now, you can click the dropdown next to *Build* again and click on the *Run* command.

![Execute Run command](./images/ws91.png?raw=true "Execute Run command")

</br></br>
   
10. After a few moments, Workspace starts the app in a temporary web server. In the gray bar for Run, at the far right, are two icons. The one that looks like a red square stops the process. The one that looks like a globe with a green dot opens up a temporary web server where the application is running. Click on the *globe* icon (or the other one in the top bar) to open the web session.

![Opening the session](./images/ws93.png?raw=true "Opening the sessionws")

**IMPORTANT NOTE: In order to see the application running in the web session, you must be logged into GitHub with the same id that you're logged in to the Workspace application.**

</br></br>

11. Once the game starts, you should see the grid on screen and can click in the squares to play, taking turns between *X's* and *O's*.

![Playing the game](./images/ws94.png?raw=true "Playing the game")   

</br></br>

12. When you're done, go back to the Workspace session and click on the red stop button.

![Stopping the game](./images/ws95.png?raw=true "Stopping the game") 

 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 4 - Making revisions in Workspace**

**Purpose: In this lab, we’ll see how to use Workspace to make revisions to our codebase**

1. While we have a version of our app that we can work with, we should also have some tests. Let's tell Workspace to add tests to our code. In the bar at the bottom, switch the mode to *Revise* again (if not already in that mode). In the bar, enter the request below to add testing to our code.

```
Add unit testing to the app
```
![Set to revise mode](./images/ws96.png?raw=true "Set to revise mode")
</br>
![Add testing](./images/ws97.png?raw=true "Add testing")
</br></br>


2. Submit this request and let it run. After processing the prompt, Copilot should update the files. Look on the right under the *Files changed* list and scroll through the changes to see what it produced.

![Files changed for testing](./images/ws98.png?raw=true "Files changed for testing")

</br></br>

3. the changes should also be listed as part of the *Plan* in the left side, under the *Task* area. Scroll down and look for files with line items with blue dots to the left of the item in the *Plan* list.

![Identifying changed files](./images/ws99.png?raw=true "Identifying changed files")

</br></br>

4. Now, let's run any updated commands. Scroll down to the *Commands* section and you'll likely see a line something like "pip install Flask pytest". Since we already have Flask installed, we just need to install pytest. We can do that through the text area at the bottom. Click to change the mode to *Command*.

![Changing mode](./images/ws101.png?raw=true "Changing mode")

5. From here, you can type in "install pytest" in the text area and submit it. After a moment, Workspace should suggest the appropriate command *pip install pytest* in a secondary popup.  They'll be an option to *Run* that command. Just click on that button.(Note: If nothing seems to happen when you click on the *Run* command, it's possible your terminal may have become disconnected. To get it back, *Reload* the page in your browser. Then try the sequence in this step again.)

![Suggest command](./images/ws102.png?raw=true "Suggest command")
</br></br>
![Run command](./images/ws103.png?raw=true "Run command")
</br></br>
![Run output](./images/ws104.png?raw=true "Run output")
</br></br>

6. Now, let's ask Copilot how to run these tests. In the bar, **switch the mode to *Ask*.** Enter the query below and submit it. Copilot should respond with some overall guidance about how to run the tests as shown in the figure.

```
How to I run the tests for this app?
```

![Switch to Ask mode](./images/ws105.png?raw=true "Switch to Ask mode")
</br></br>
![Testing guidance](./images/ws106.png?raw=true "Testing guidance")
</br></br>

7. Ultimately, the testing boils down to just running "pytest". So, let's just switch to the *terminal* and run the command ourselves. Click on the *Commands* tab and the *Terminal*. Then, just enter "pytest". (**NOTE: It is highly likely that your tests may still have some pieces that need to be tweaked and may not run correctly right now.**)

```
pytest
```

![Create repo](./images/ws107.png?raw=true "Create repo")
</br></br>

8. The commands may execute correctly or not. If they don't run correctly, you can come back later and debug. For now, we'll go ahead and add this code into a new GitHub repository like we did in lab 1.8. In the upper right of the main Workspace screen, click on the *Create repository* screen.

![Create repo](./images/ws5.png?raw=true "Create repo")
</br></br>

9. As in Lab 1, clicking on this button opens a dialog with a suggested name for the repo and a place for a description. Let's update the suggested repository name so it doesn't conflict with the existing one. (I added a "-v2" suffix.) The dialog includes the button to click to automatically generate the initial commit message. Click on that.

![Generate commit info](./images/ws108.png?raw=true "Generate commit info")
</br></br>

10. After generating the description and clicking on the button, GitHub creates the repo and presents you with a dialog to *Open in GitHub* or *Start new session*. Click on *Open in GitHub*.
   
![Open in GitHub](./images/ws110.png?raw=true "Open in GitHub")
</br></br>
![Opening in GitHub](./images/ws109.png?raw=true "Opening in GitHub")



 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 5 - Leveraging Workspace from an existing repository**

**Purpose: In this lab, we’ll see how to make revisions with Workspace starting from an existing repository**

1. While we have a version of our app that we can work with, we might like to add some additional features. For example, let's add a feature to play against the computer. Since we have an existing repository, we can initiate the Workspace process from there. For formal tracking, let's first open a GitHub issue for the feature. You'll need to make sure the Issues functionality is turned on for your repository. Go to the *Settings* tab for the repository and then scroll down until you find the Issues checkbox and make sure it's checked. (The URL is https://github.com/_userid_/_repository_/settings )

![Activating issues](./images/ws111.png?raw=true "Activating issues")
</br></br>

2. Now, let's create a new issue for the feature request. Click on *Issues* at the top and then click on the button to create a new issue.

![Creating new issue](./images/ws24.png?raw=true "Creatinge new issue")
</br></br>

3. For the issue title, you can fill in something like the text below:

```
Add option to play against the computer
```
</br></br>

4. For the issue description, you can add something like the text below:

```
The game should have the ability for the user to play against the computer. The player and the computer should take turns filling in their squares. The ability to play against the computer should be an option the main web page.
```

![Filling in issue fields](./images/ws25.png?raw=true "Filling in issue fields")
</br></br>

5. When you're done, scroll down and click on the *Create* button to create the issue.

![Creating the issue](./images/ws112.png?raw=true "Creating the issue")
</br></br>

6. Now, we'll shift to working in Workspace. To get to Workspace from within an existing repository, first go back to the "<> Code" tab at the top of the repo. On that page, click on the green <> Code button above the list of files on the right. There, you'll have a Copilot tab (in addition to the Local and Codespaces tabs). Clicking on the Copilot tab gives you a dialog box to describe a task. We'll simply tell Copilot to address the issue we just opened. For example, you can just enter the text below in the *Copilot* tab.

```
Address issue #1
```

![Filling in Copilot field](./images/ws113.png?raw=true "Filling in Copilot field")
</br></br>

7. Click on *Start task*. This should open up a new Workspace based on this repository. The Workspace is populated with Current behavior, and Proposed solution sections based on the content of the repository and the issue (#workspace-for-issue). The Current behavior section details what the repository has, and does not have, relative to the requested task. Scroll through the contents of the *Current behavior* area and look at the current assessment. The Proposed solution section details what Copilot plans to change/add to the current code to accomplish the task. Scroll through and take a look at the contents of both sections.

![Current and proposed](./images/ws114.png?raw=true "Current and proposed")
</br></br>

8. You also have a set of *Suggested questions* at the bottom of the right side. You can choose from these as before to see additional options you can add to your app. If you find one that you like, you can click on the *+ Add to task* button. In the example shown in the figure, we've chosen to have *Adjustable difficulty levels* added from one of the suggested questions.

![Item added from question](./images/ws116.png?raw=true "Item added from question")
</br></br>

9. Back on the left side, at the bottom of the *Task* area, you may notice there's a section called *Additional context* that references a URL. If you expand that, you'll see that Workspace is using the URL of the issue we opened as context.

![Additional context from issue URL](./images/ws117.png?raw=true "Additional context from issue URL")
</br></br>
 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 6 - Updating a repository from a Workspace**

**Purpose: In this lab, we’ll see how to add updates from a Workspace back to an existing repository**

1. Since we've got our changes established now, we can just proceed with the usual process to get to code in a Workspace. Start that by clicking on the green button in the *Task* area for *Generate plan* to generate the plan to handle the issue.
</br></br>

2. You can scan through the listed items in the plan. Then proceed by clicking on the *Implement selected files* entry at the bottom of the *Plan* area.
</br></br>

3. After the generation completes, review the proposed changes on the right side.

![Reviewing proposed changes](./images/ws118.png?raw=true "Reviewing proposed changes")
</br></br>

4. From here, we can open up the commands dialog so we can run our app. In the top row, click on the *Commands* icon (the one that looks like a terminal). After clicking this, it will take a moment for Workspace to connect to a terminal.

![Opening commands](./images/ws119.png?raw=true "Opening commands")
</br></br>

5. You may already have the command populated in the *Run* field. If so, you can use that one. If not, you can just enter the command below or click on the light bulb.

```
pip install -r requirements.txt && python app.py
```

![Run command](./images/ws120.png?raw=true "Run command")
</br></br>

6. Execute the *Run* command by clicking on the play button at the end of the line. (Alternatively, you could switch to the terminal and run the command there.)  Once the command starts, click on the globe icon to open the live preview as before. 

![Run command](./images/ws121.png?raw=true "Run command")
</br></br>
    
7. At this point, you should see your updated game. (Hopefully this works as expected, but even if not, just proceed with the following steps for now.)

![Run command](./images/ws122.png?raw=true "Run command")
</br></br>

8. With our changes made in the code and tested, we're ready to create a pull request for our repository to fix the issue. Click the *Create pull request* button in the upper right. (Note there are various other related options available via the drop-down if needed.), 

![Create pull request](./images/ws123.png?raw=true "Create pull request")
</br></br>

9. You can use the suggested branc name for the pull request and click the option to generate a description. You may have a box available to check that this pull request fixes issue #1. If so, check that. If not, add "Fixes #1" at the start of the description. Then click on the *Create pull request* button.

![Create pull request](./images/ws124.png?raw=true "Create pull request")
</br></br>

10. In the dialog box that pops up, click on the *Open in GitHub* button or manually go to the repo in GitHub. 

![Open in GitHub](./images/ws125.png?raw=true "Open in GitHub")
</br></br>

11. Now, in GitHub, you can merge the pull request. For completeness, you can add "Fixes #1" in the Extended Description here too. Afterwards your changes are merged and the issue should be closed.
</br></br>

 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>
