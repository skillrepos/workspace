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

5. Let's give Workspace a goal to create a simple tic-tac-toe game. In the task area, enter the command below.

```
create a tic-tac-toe game
```

6. Now, let's cut straight to the implementation. Click on the green *Generate plan* button below the dialog area and then select tehe 
   
![Creating file from terminal](./images/cdd173.png?raw=true "Creating file from terminal")

2. Afterwards this file should be open in a tab in the editor.

3. Let's see how Copilot responds to a generic request. Go to that tab and type in a comment that says

```
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
