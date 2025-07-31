# Meet App

Meet is a serverless, progressive web application (PWA) built with React and Vite. It uses the Google Calendar API to fetch upcoming events and supports offline usage, dynamic filtering, and data visualization. The app is designed using a test-driven development (TDD) approach with clear test scenarios to ensure quality and functionality.

## Key Features

- Filter events by city
- Show/hide event details
- Specify number of events to display
- Offline support with service worker caching
- Installable as a home screen shortcut
- Data visualization with charts (events by city and by genre)

---

## User Stories (Features 2–6)

**Feature 2: Show/Hide Event Details**

- As a user, I should be able to expand and collapse an event  
  So that I can read more or less information as needed

**Feature 3: Specify Number of Events**

- As a user, I should be able to choose how many events are displayed  
  So that I can control the amount of information shown

**Feature 4: Use the App When Offline**

- As a user, I should be able to view cached events while offline  
  So that I can still use the app without an internet connection

**Feature 5: Add Shortcut to Home Screen**

- As a user, I should be able to install the app as a shortcut  
  So that I can quickly access it like a native app

**Feature 6: Display Charts Visualizing Event Details**

- As a user, I should see charts that visualize event locations and genres  
  So that I can quickly understand trends at a glance

---

## Feature 1: Filter Events By City

**User Story:**  
As a user, I should be able to filter events by city so that I can see a list of events in that location.

**Scenarios:**

**Scenario: Show events from all cities when no city is searched**  
Given the user hasn’t searched for any city  
When the user opens the app  
Then the user should see a list of upcoming events

**Scenario: Show suggestions when user types in a city**  
Given the main page is open  
When the user starts typing in the city textbox  
Then the user should receive a list of cities (suggestions) that match what they’ve typed

**Scenario: User can select a city from the suggested list**  
Given the user was typing “Berlin” in the city textbox and suggestions are showing  
When the user selects “Berlin, Germany” from the list  
Then the city should be changed to “Berlin, Germany” and the user should see upcoming events in that city

---

## Feature 2: Show/Hide Event Details

**User Story:**  
As a user, I should be able to expand and collapse event details so that I can read more or less information as needed.

**Scenarios:**

**Scenario: Event element is collapsed by default**  
Given the user has opened the app  
When the list of events is displayed  
Then each event element should show only the event summary without details

**Scenario: User can expand an event to see details**  
Given the list of events has been loaded  
When the user clicks on the “Show details” button for an event  
Then the event element should expand to display the event’s details

**Scenario: User can collapse an event to hide details**  
Given the list of events has been loaded  
When the user clicks on the “Hide details” button for an event  
Then the event element should collapse to show only the event summary

---

## Feature 3: Specify Number of Events

**User Story:**  
As a user, I should be able to choose how many events are displayed so that I can control the amount of information shown.

**Scenarios:**

**Scenario: Show 32 events by default**  
Given the user has not specified a number of events to display  
When the user opens the app  
Then the user should see a list of 32 upcoming events

**Scenario: User can change the number of events displayed**  
Given the main page is open and the events list is loaded  
When the user changes the number of events in the input field  
Then the user should see that number of events displayed

---

## Feature 4: Use the App When Offline

**User Story:**  
As a user, I should be able to view cached events while offline so that I can still use the app without an internet connection.

**Scenarios:**

**Scenario: Show alert when app is offline**  
Given the user has no internet connection  
When the user reloads the page  
Then the user should see an alert message indicating they are offline

**Scenario: Show error when search settings are changed while offline**  
Given the user is offline and the app is showing cached events  
When the user changes the city or number of events  
Then the user should see an alert message indicating that search is not available offline

---

## Feature 5: Add App Shortcut to Home Screen

**Note:** This feature is handled by the device’s operating system and cannot be tested with automated test scenarios.

---

## Feature 6: Display Charts Visualizing Event Details

**User Story:**  
As a user, I should see charts that visualize event locations and genres so that I can quickly understand trends at a glance.

**Scenarios:**

**Scenario: Show chart of upcoming events by city**  
Given the user has opened the app and the list of events has been loaded  
When the chart is rendered  
Then the user should see a chart displaying the number of upcoming events for each city

**Scenario: Show chart of event genre popularity**  
Given the user has opened the app and the list of events has been loaded  
When the genre chart is rendered  
Then the user should see a chart displaying the popularity of each event genre
