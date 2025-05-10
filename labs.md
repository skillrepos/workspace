# Working with GitHub Copilot Workspace
## From concept to code using Gen AI
## Revision 1.0 - 05/10/25

**Versions of dialogs, buttons, etc. shown in screenshots may differ from current version of Copilot**

**Follow the startup instructions in the README.md file IF NOT ALREADY DONE!**

**NOTES:**
1. We will be working in the public GitHub.com as our backing repository, not a private instance.
2. VPNs may interfere with the ability to run the codespace. It is recommended to not use a VPN if you run into problems.
6. If you use the new free Copilot plan (no signup), some advanced functionality may not be available.
</br></br></br>
   
**NOTE: You must be on one of the paid plans to have access to Workspace.**

**Lab 1 - A quick run-through of using Workspace**

**Purpose: In this lab, we’ll start to learn about Copilot Workspace and how it generates code based on the prompts we provide**

1. Open a browser session and go to this link [New Workspace Session](https://copilot-workspace.githubnext.com)

2. If you're not already signed in, you'll need to sign in with your GitHub userid and password.

![Sign-in needed](./images/ws1.png?raw=true "Sign-in needed")

3. You'll then need to authorize your GitHub account.

![Authorize](./images/ws2.png?raw=true "Authorize")

4. We're going to create a project from scratch, so click on the *Create new repository* link.

![Create new repository start](./images/ws3.png?raw=true "Create new repository start")

5. Let's give Workspace a goal to create a simple tic-tac-toe game. In the task area, enter the command below.

```
create a tic-tac-toe game
```

![Add new goal](./images/ws4.png?raw=true "Add new goal")

6. Now, let's cut straight to the implementation. Click on the green *Generate plan* button below the dialog area and then select the *Generate Code* button.

![Generate code](./images/ws4.png?raw=true "Generate code")

7. This will run for a while to generate all the code for your project.

8. After this is done, we'll create a repository to put our code in. In the upper right of the main Workspace screen, click on the *Create repository* screen.

![Create repo](./images/ws5.png?raw=true "Create repo")

9. Clicking on this button opens a dialog with a suggested name for the repo and a place for a description. The dialog includes a button to click to automatically generate the initial commit message. Click on that.

![Generate commit info](./images/ws6.png?raw=true "Generate commit info")

10. After generating the description and clicking on the button, GitHub creates the repo and presents you with a dialog to *Open in GitHub* or *Start new session*. Click on *Open in GitHub*.
   
![Opening in GitHub](./images/ws7.png?raw=true "Opening in GitHub")

11. From here, you can clone your repository down locally and then run it - usually by opening up the index.html file.

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


**Lab 2 - A more refined game**

**Purpose: In this lab, we’ll create a more defined instance of our game by working through the formal process**

1. Let's start by adding a very specific definition to Workspace of what we want. We wouldn't have to be this specific at all, but this will help ensure we get more accuracy and consistency in the result. In the task area, copy and paste the following requirement.

```
Add Tic-Tac-Toe Game

Task:
  • Implement a browser-based Tic-Tac-Toe game playable by two users  
  • Render a 3×3 grid of clickable cells  
  • Alternate X and O marks on each click  
  • Detect and display when one player wins or when the game is a draw  
  • Provide a “Restart” button to reset the board  

Dependencies & Components:
  • UI framework: React (v18+) **or** vanilla HTML/CSS/JS  
  • Files:  
      – `index.html` (root container)  
      – `styles.css` (grid layout & styling)  
      – `App.jsx` or `app.js` (game logic & rendering)  
      – `GameBoard.jsx` / `GameBoard.js` (grid component)  
      – `Square.jsx` / `Square.js` (cell component)  
  • Core functions:  
      – `handleClick(cellIndex)` to place mark  
      – `calculateWinner(cells: string[9]) → string|null`  
      – `resetGame()` to clear board state  

Acceptance Criteria:
  • A 3×3 board appears on page load  
  • Clicking an empty cell places “X” then “O” on alternating turns  
  • When three in a row appear (horiz, vert, diag), show “Player X wins!” or “Player O wins!”  
  • If all cells fill without a winner, display “Draw”  
  • “Restart” button clears the board and resets turn order  
```

![Detailed requirements](./images/ws9.png?raw=true "Detailed requirements")

2. Now, click the *Brainstorm* button to go to the initial *brainstorming/planning* page.

![Brainstorm](./images/ws10.png?raw=true "Brainstorm")

3. On the right will be a *Brainstorm* section showing different ideas and approaches you can have Workspace implement for you. These ideas range from basic implementation approaches to suggested options and possible advanced features. You can scroll through the ones that are listed and decide if you want to add any of them as additional tasks to the overall plan that Copilot has constructed. To add them, click the corresponding *+ Add to task* button.

![Brainstorm list](./images/ws11.png?raw=true "Brainstorm list")

4. At the bottom of the *Ideas* list will be a *Suggested questions* section with some other ideas from Copilot on areas to explore and/or validate. You can scroll down and click on a particular question to see what Copilot would propose for it. This will usually show a series of suggested implementation details relevant to the overall question.

![Suggested questions](./images/ws12.png?raw=true "Suggested questions")

5. Pick one if you want and click on the *+ Add to task* button to add it into the *Tasks* area as one of the *Ideas from brainstorming*.

![Adding items from question](./images/ws13.png?raw=true "Adding items from question")

6. With our set of initial tasks defined, we're ready to proceed to generating the plan. On the left side of the dashboard, click the *Generate plan* button.

![Generating the plan](./images/ws14.png?raw=true "Generating the plan")

7. Copilot will process for a few moments and then add a *Plan* section on the left under the *Task* area. This section lists out all the files it expects to create along with the main logic that will be implemented in each.

![Plan section](./images/ws15.png?raw=true "Plan section")

8. If we were implementing changes against an existing code base, we would see diffs here for existing files. Since we don't yet have any actual files, we just see the list and names. 

![Planned files](./images/ws16.png?raw=true "Planned files")


 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 3 - Running the example**

**Purpose: In this lab, we’ll see how to complete the code generation and run the example.**

1. Now that we have our plan in place, we can go ahead and have Workspace create the initial version of the files. At the bottom of the *Task/Plan* area is a button to *Implement selected files*. In the *Plan* area, make sure that all files are checked (check in the box). Then click on the *Implement selected files* button to have Copilot generate the selected files.

![Generate files](./images/ws17.png?raw=true "Generate files")

2. After the code generation completes, the *Files changed* section will show the proposed implementations. Scroll through and review the proposed changes. You also have an option to add additional features to a file by using the *+ Add item entry* in the file's section on the Plan.


![Proposed code](./images/ws18.png?raw=true "Proposed code")

3. Back on the left side, in the *Plan* area, there may be a section at the bottom titled *Commands* that contains any terminal commands that need to be executed. If so, click on the *play* button next to the the command(s) to automatically open a terminal and execute the command. After running it will be checked off as completed in the task list.


![Running commands](./images/ws19.png?raw=true "Running commands")

4. In the top row of controls is a section of icons for starting other dev interfaces, including ones to open a dialog for commands and a terminal, one to open a GitHub Codespace, and one to open the code in VS Code. Click on the one to open *commands/terminal*.

![Dev interfaces](./images/ws20.png?raw=true "Dev interfaces")


5. Workspace presents us with a screen where we can enter standard commands to build, test, and run our code.  You can input a command directly in the appropriate field or click on the light bulb icon at the end to have Copilot suggest a command. Since this is a flask app, we can just add the command flask run for the Run entry.


![Run command](./images/ws21.png?raw=true "Run command")

6. After a few moments, Workspace starts the app in a temporary web server. In the gray bar for Run, at the far right, are two icons. The one that looks like a red square stops the process. The one that looks like a globe with a green dot opens up a temporary web server where the application is running. After clicking on that, we can view the running application and start playing the game.

![Playing the game](./images/ws22.png?raw=true "Playing the game")

7. When you're done, click on the red stop button.

 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 4 - Making revisions**

**Purpose: In this lab, we’ll see how to make revisions to our codebase.**

1. While we have a version of our app that we can work with, we should also have some tests. Let's tell Workspace to add tests to our code. In the bar at the bottom, switch the mode to *Revise*. In the bar, enter the request below to add testing to our code.

```
Task: 
- Add unit testing to the app

Dependencies & Components:
- Jest

Acceptance Criteria:
- Unit tests pass for all win/draw scenarios
```
 
![Add testing](./images/ws18.png?raw=true "Add testing")

2. Submit this request and let it run. After processing the prompt, Copilot should update the files and the changes should also be listed as part of the plan in the left side. Go ahead and click the *Generate code* button again for the updated plan.

![Testing added](./images/ws19.png?raw=true "Testing added")

3. Now, let's ask Copilot how to run these tests. In the bar, switch the mode to *Ask*. Enter the query below and submit it.

```
How to I run the tests for this app?
```

4. Copilot should respond with some text about how to run the set of tests it added. Copy the commands.


![Testing added](./images/ws20.png?raw=true "Testing added")

5. Now, let's open up the terminal and try out the testing commands. Click on the *Commands/Terminal* control again and select the *Terminal* tab.

![Getting to terminal](./images/ws21.png?raw=true "Getting to terminal")

6. In the terminal, paste the commands from step 4 above and execute them.

![Running testing commands](./images/ws22.png?raw=true "Running testing commands")

7. The commands may execute correctly or not. If they don't run correctly, you can come back later and debug. For now, we'll go ahead and add this code into a new GitHub repository like we did in lab 1.

8. In the upper right of the main Workspace screen, click on the *Create repository* screen.

![Create repo](./images/ws5.png?raw=true "Create repo")

9. Clicking on this button opens a dialog with a suggested name for the repo and a place for a description. The dialog includes a button to click to automatically generate the initial commit message. Click on that.

![Generate commit info](./images/ws6.png?raw=true "Generate commit info")

10. After generating the description and clicking on the button, GitHub creates the repo and presents you with a dialog to *Open in GitHub* or *Start new session*. Click on *Open in GitHub*.
   
![Opening in GitHub](./images/ws7.png?raw=true "Opening in GitHub")



 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 5 - Making changes in an existing repository**

**Purpose: In this lab, we’ll see how to make revisions with Workspace in an existing repository.**

1. While we have a version of our app that we can work with, we might like to add some additional features. For example, let's add a feature to play against the computer. Since we have an existing repository, we can initiate the Workspace process from there. For formal tracking, let's first open a GitHub issue for the feature. You'll need to make sure the Issues functionality is turned on for your repository. Go to Settings and then scroll down until you find the Issues checkbox and make sure it's checked.

![Activating issues](./images/ws23.png?raw=true "Activating issues")


2. Now, let's create a new issue for the feature request. Click on *Issues* at the top and then click on the button to create a new issue.

![Creating new issue](./images/ws24.png?raw=true "Activating issues")

3. For the issue title, you can fill in something like the text below:

```
Add option to play against the computer
```

4. For the issue description, you can add something like the text below:

```
The game should have the ability for the user to play against the computer. The player and the computer should take turns filling in their squares. The ability to play against the computer should be an option the main web page.
```


![Filling in issue fields](./images/ws25.png?raw=true "Filling in issue fields")

5. To get to Workspace from within an existing repository, first click on the green <> Code button in the repository. There, you'll have a Copilot tab (in addition to the Local and Codespaces tabs). Clicking on the Copilot tab gives you a dialog box to describe a task. We'll simply tell Copilot to address the issue we just opened. For example, you can just enter the text below in the *Copilot* tab.

```
Address issue #1
```

![Filling in Copilot field](./images/ws26.png?raw=true "Filling in Copilot field")

6. Click on *Start task*. This should open up a new Workspace based on this repository. The Workspace is populated with Current behavior, and Proposed solution sections based on the content of the repository and the issue (#workspace-for-issue). The Current behavior section details what the repository has, and does not have, relative to the requested task. Scroll through the contents of the *Current behavior* area and look at the current assessment.


![Current behavior](./images/ws27.png?raw=true "Current behavior")
  
  
7. The Proposed solution section details what Copilot plans to change/add to the current code to accomplish the task. Scroll through and take a look at the contents of that section.


![Proposed solution](./images/ws28.png?raw=true "Proposed solution")

8. From here, we just follow the usual workflow by generating the plan, reviewing it, and when ready, generating the code. After reviewing the proposed changes, go ahead and click on the button to generate the updated plan*.

![Updated plan](./images/ws29.png?raw=true "Updated plan")

9. Now, review the plan and generate the code.


![Generate updated code](./images/ws30.png?raw=true "Generate updated code")

10. From here, we can open and run it just as we did in the last lab to try it out.
   

11. 
// function to parse data
```
4. Hit return and notice the code that Copilot suggested. This is likely more generic than we want, but hit tab to select that line. (Note that you should give Copilot a second to provide code suggestions before moving on to the next line.)
   
5. After hitting tab, Copilot will generate another part of the function. (If not, you may need to hit return.) Hit tab to accept it. Continue until you get a complete function (or Copilot stops generating additional code suggestions). One example of what code may look like is below. (This likely won't be the same as yours.)

![Copilot generated function](./images/cdd2.png?raw=true "Copilot generated function")
   
6. This prompt is not specific enough for Copilot to interpret what we want to do.  Highlight the code and delete it, so we can try again.

7. Now type a comment at the top that says

```
// function to parse url
```
8. Hit enter and you will probably see a similar line to

```
function parseURL(url) {
```

9. Just hit Tab to accept it and Enter again. Pause. After that Copilot may or may not offer a suggestion.  If it does, great - you can just hit Tab and accept it.  If not, it may be necessary to further "nudge" Copilot by giving more prompts. Only if you're not getting responses from Copilot, hit return and type the comment below to nudge Copilot.

```
// parse url
```
![nudge comment](./images/cdd3.png?raw=true "nudge comment")   

10. Only if needed, hit return and Copilot should start generating suggestions again. Pause after each return to give Copilot a chance to suggest code. Then you can just hit tab to accept each line and then return to get the next part of the code until the function is complete. You may get some blank lines along the way or for some lines you might need to hit Tab twice to accept the code if it is indented more. But just hit return until you get to the end of a function. (You will be at the end when the indentation is done.  Also Copilot may start to suggest another function in comments like // test...)

11. Suppose you're not happy with that suggestion. Copilot can provide other options for the code. To see those, make sure you are in the editor for the file, then delete all but the first line of the function **and** put the cursor at the end of the first line.

![reset for altenate choices](./images/cdd105.png?raw=true "reset for alternate choices")   
   
12. Hit **Ctrl + Enter**. A second window will open up with other suggestions.
Be patient - it takes a bit of time for Copilot to generate alternative suggestions. After a moment though, you will have up to 10 alternatives to pick from. These will be of varying quality and completeness. You can scan through these and then pick one if suitable by clicking on the **Accept suggestion #** button under the alternative suggestion.  Note that this will add the code to the existing set, so you may need to do some minor editing afterwards.

![alternative suggestions](./images/cdd106.png?raw=true "alternative suggestions")   

13. Let's do one more pass at getting a specific prompt for Copilot. Delete all the code currently in index.js. This time we will not enter a comment, but will enter a specific function name.
Type the following in the empty file. (There are no parentheses after the *splitURLandReturnComponents* text.)  Do not hit tab or return yet.

```
function splitURLandReturnComponents
```

14.  With this function name, Copilot should suggest a full function definition - in fact it may suggest several.  To see the options, hover over the first line and a small window should appear. This window will not how many options there are (probably 2 or 3) and provide "<" and ">" links to toggle between them.  Click on the "<" and ">" buttons to see the differences in the available suggestions.

![alternative suggestions inline](./images/cdd5b.png?raw=true "alternative suggestions inline")   

15. When you find an alternative you like, go ahead and tab to select it.

 <p align="center">
**[END OF LAB]**
</p>
</br></br></br>

**Lab 2 - Using Copilot to simplify code**
