# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.

MeetMap
MeetMap is a progressive web app that helps users find upcoming events in any city. Below are the core features expressed as Gherkin scenarios.

Show/Hide Event Details
Feature: Toggle event details

Scenario: Event details are hidden by default
Given the user is viewing a list of events
Then the event details should be collapsed by default

Scenario: User expands event details
Given the user is viewing a list of events
When the user clicks the "Show Details" button on an event
Then the event details should be expanded

Scenario: User hides event details again
Given the event details are currently expanded
When the user clicks the "Hide Details" button
Then the event details should be collapsed

Specify Number of Events
Feature: Specify number of events

Scenario: Default number of events is shown
Given the user has not specified a number
Then 32 events should be displayed by default

Scenario: User specifies a number of events to display
Given the user is on the event list page
When the user enters "10" into the number of events input field
Then only 10 events should be displayed

Use the App When Offline
Feature: Use app offline

Scenario: User opens app with no internet connection
Given the user has previously loaded the app online
And the user loses internet connection
When the user opens the app
Then cached event data should be displayed

Scenario: User changes settings while offline
Given the user is offline
When the user changes the city or number of events
Then an error message should be shown

Add an App Shortcut to the Home Screen
Feature: Add app to home screen

Scenario: User installs the app to home screen
Given the user is using a supported browser
When the browser prompts to add the app to the home screen
And the user accepts
Then the MeetMap app should be installed as a shortcut on the home screen

Display Charts Visualizing Event Details
Feature: Display event data visualizations

Scenario: Display chart for events per city
Given the user is viewing the main page
When events are loaded
Then a chart should be displayed showing the number of upcoming events in each city

Scenario: Display chart for event genres
Given the user is viewing the main page
When events are loaded
Then a pie chart should be displayed showing the popularity of each event genre
