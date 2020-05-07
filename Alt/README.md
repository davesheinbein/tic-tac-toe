# tic-tac-toe

Analyze the app's functionality

The app's features, from the user's point of view, should be described using User Stories. User stories follow this template: As a [role], I want [feature] because [reason]. Example user story: As a player, I want to see a list of high-scores so that I know what I have to score to make the list.
Think about the overall design (look & feel) of the app

Take the users (audience) of the app into consideration.
Should the app have a clean/minimalist UI (current trend), or should it be themed to match the app's purpose?
Wireframe the UI

Wireframes provide a blueprint for the HTML & CSS.
Wireframes also help reveal an application's data (state) and functionality.
Pseudocode

Some of the app's features may need to be pseudocoded, that is, outlining the app's logic in a plain, informal way.
Pseudocode the app's overall functionality first.
More detailed pseudocode for a given feature may be required later.
Analyze the application's state (data)

What does the application need to "remember" throughout its execution?
Use the wireframe(s), user stories and pseudocode to help determine what state needs to be tracked.
Note that in an application with a database, we would analyze the database design during this step.
Set up the project

Create project directory OUTSIDE of any existing git repo (nested repos cause problems).
Create the starting project files. Here's a possible structure:
index.html
css/main.css
js/main.js
Create the HTML boilerplate within index.html.
Link main.css in the <head>.
Loading main.js just above the closing </body> tag ensures that the DOM is ready before the script runs. Alternatively, if you want to put the script tag in the <head>, add a defer attribute as follows:
<script defer src="js/main.js">
Be sure to load libraries such as jQuery before the app's scripts.
Create a local repo

$ git init
Create a remote repo in your GitHub account then follow the instructions that GitHub provides to add a remote to link your local repo to GitHub.
It is recommended that the name of the repo and the project directory match.
Organize the app's JS into sections

Adding comments such as the following will help you organize your app's code:
/*----- constants -----*/
/*----- app's state (variables) -----*/
/*----- cached element references -----*/
/*----- event listeners -----*/
/*----- functions -----*/
Code away!

Iterating between adding HTML, CSS & JS is one approach.
Start with some markup for the basic layout of the UI.
Declare, but don't initialize, the application-wide variables (state). The initialization of the variables to their "start-up" state should be done within an initialize, or similarly named function, i.e., init, reset, etc.
Write that initialize function.
Invoke initialize() to "kick off" the app.
Next stub up a render function. Be sure to call render after state has been updated in event handlers, the initialize function, etc.
Register event listeners - browser apps are typically event-driven.
If you have user stories, code them in a logical order.
More recommendations for interactive browser app's, such as games

Create a main render function that is responsible for rendering the state of the app to the DOM.
If the render function becomes lengthy, add additional rendering oriented functions, for example:
function render() {
	renderHands();
	renderControls();
	if (winner) {
		renderWinnerMessage();
	} else {
		renderTurnMessage();
	}
}
Avoid accessing the DOM from outside render-oriented functions. However, "eye candy" animations, a ticking time display, etc. are exceptions to this tip.
Data (state) is the single source of truth of the app - when implementing an app's logic, the DOM is secondary to data manipulation. Get used to thinking about how to your app's data changes vs. the display.
As the user interacts with the application (or other events such as timers trigger), code the app such that it:
Updates state, then...
Calls render()
Make frequent git commits of working code

At a minimum, commit each "milestone" or feature implementation.
Experiment and refactor code as necessary

Have fun!