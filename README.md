# Google-Meeting-Scheduler


```


<script src="https://apis.google.com/js/api.js"></script>
<script>
  // Client ID and API key from the Google Developers Console
  var CLIENT_ID = 'YOUR_CLIENT_ID';
  var API_KEY = 'YOUR_API_KEY';

  // Array of API discovery doc URLs for APIs used by the quickstart
  var DISCOVERY_DOCS = ["https://www.googleapis.com/discovery/v1/apis/calendar/v3/rest"];

  // Authorization scopes required by the API; multiple scopes can be
  // included, separated by spaces.
  var SCOPES = "https://www.googleapis.com/auth/calendar.events";

  var authorizeButton = document.getElementById('authorize-button');
  var signoutButton = document.getElementById('signout-button');

  /**
   *  On load, called to load the auth2 library and API client library.
   */
  function handleClientLoad() {
    gapi.load('client:auth2', initClient);
  }

  /**
   *  Initializes the API client library and sets up sign-in state
   *  listeners.
   */
  function initClient() {
    gapi.client.init({
      apiKey: API_KEY,
      clientId: CLIENT_ID,
      discoveryDocs: DISCOVERY_DOCS,
      scope: SCOPES
    }).then(function () {
      // Listen for form submission
      document.getElementById('meeting-form').addEventListener('submit', createEvent);
    }, function(error) {
      // Handle error
      console.log(error);
    });
  }

  /**
   *  Creates a calendar event based on the user's input.
   */
  function createEvent(event) {
    event.preventDefault();
    var title = document.getElementById('title').value;
    var start = new Date(document.getElementById('start-time').value);
    var end = new Date(document.getElementById('end-time').value);
    var attendees = document.getElementById('attendees').value.split('\n');
    var event = {
      'summary': title,
      'start': {
        'dateTime': start.toISOString()
      },
      'end': {
        'dateTime': end.toISOString()
      },
      'attendees': attendees.map(function(email) {
        return {'email



```
