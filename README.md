Academic Planner
A single-page web application that provides an interactive Gantt chart to manage the academic year's schedule for the Computing and Engineering departments at a UK-based university. This tool helps administrative teams to centralize their schedule, improve efficiency, and enhance collaboration.

✨ Features
Interactive Gantt Chart: View all academic activities on a timeline to visualize durations, overlaps, and key dates.

Detailed Activity List: See a card-based view of activities with detailed information.

CRUD Functionality:

Create: Add new activities through a modal form, specifying details like activity name, category, dates, and responsible team.

Update: Edit existing activities.

Delete: Remove activities with a confirmation step.

Real-time Updates: Changes made by any user are reflected in real-time for all other users.

Filtering and Searching:

Filter activities by category to focus on specific areas of responsibility.

Search for activities by keywords across all fields.

Responsive Design: The application is fully responsive and accessible on desktop, tablet, and mobile devices.

🚀 Tech Stack
Frontend:

HTML5

Tailwind CSS

Vanilla JavaScript

Chart.js for the Gantt chart visualization.

Backend:

Google Firebase

Firestore: A NoSQL database used for storing all activity data.

Firebase Authentication: For handling user sessions via anonymous authentication.

Firebase Hosting: The recommended platform for deployment.

⚙️ Getting Started
Prerequisites
Node.js

Firebase Tools (npm install -g firebase-tools)

Installation
Clone the repository:

Bash

git clone https://github.com/arsenal86/academicplanner.git
cd academicplanner
Set up Firebase:

Create a new project in the Firebase Console.

Create a firestore.rules file with the following rules to allow read and write access for authenticated users:

rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
In the index.html file, replace the placeholder Firebase configuration with your project's configuration. You can find this in your Firebase project settings.

JavaScript

const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_AUTH_DOMAIN",
    projectId: "YOUR_PROJECT_ID"
};
Deploy the project:

Bash

firebase deploy --only hosting,firestore
Usage
Once the application is deployed, you can access it via the hosting URL provided by Firebase. The application will be pre-populated with initial data for the academic year 2025-2026.

Filtering: Click on the category buttons to filter the Gantt chart and activity list.

Searching: Use the search bar to find specific activities.

Adding an Activity: Click the "Add New Activity" button to open a modal where you can enter the details of the new activity.

Editing an Activity: Click the "Edit" button on an activity card to modify its details.

Deleting an Activity: Click the "Delete" button on an activity card and confirm the action in the dialog.

🚀 Deployment
The application is designed to be deployed using Firebase Hosting. The firebase.json file is configured to serve the index.html file as the main entry point for all routes.

To deploy the application, run the following command in the project's root directory:

Bash

firebase deploy
