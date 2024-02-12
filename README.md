# Google Calendar Python Module

## Introduction
The Google Calendar Python Module is a versatile library designed by Bruno Caracini to interact with the Google Calendar API seamlessly. It provides functionalities to create, retrieve, and manipulate events within Google Calendar, making it an essential component for applications that require integration with Google's scheduling services.

## Features

- **Authentication**: Utilizes OAuth2 authentication with service account credentials for secure server-to-server access to Google APIs.
- **Calendar Operations**: Supports operations such as retrieving calendar IDs, fetching events, creating new events, and removing events from calendars.

## Prerequisites

Before using the Google Calendar Python Module, ensure that you have the following:

- **Google Cloud Platform (GCP) Project**: You need to have a GCP project set up where you can create a service account for authentication. If you don't have a GCP project, you can create one [here](https://console.cloud.google.com/projectcreate).
  
- **Service Account (SA)**: Create a service account within your GCP project. This service account will be used for authentication with the Google Calendar API. Make sure to download the JSON key file associated with the service account, as it will be needed to authenticate the module.

- **Calendar Sharing**: If you intend to access calendars that are not owned by the service account, ensure that those calendars are shared with the service account. This is necessary to grant the required permissions for reading, modifying, or deleting events from those calendars.

## Installation

To use the Google Calendar Python Module in your project, follow these steps:

1. Install the required dependencies by running:

    ```bash
    pip install -r requirements.txt
    ```

2. Import the module into your Python script:

    ```python
    from google_calendar import GoogleCalendar
    ```

## Usage

### Authentication
Before using any functionalities of the module, ensure that you have set up OAuth2 authentication with a valid service account JSON key file. Set the path to the key file in your environment variables as `GOOGLE_CALENDAR_KEY_FILE_LOCATION`.

### Example Usage

```python
from google_calendar import GoogleCalendar

# Retrieve calendar IDs
calendar_ids = GoogleCalendar.get_calendar_ids()

# Fetch events for a specific calendar
events = GoogleCalendar.get_events_for_calendar(calendar_id='your_calendar_id', max_results=10)

# Create a new event
event = GoogleCalendar.create_event(summary='Meeting', description='Team meeting', start=start_time, end=end_time)
```

## Notes

- **Error Handling**: The module handles HTTP errors gracefully and logs them for troubleshooting purposes.
- **Scopes**: Ensure that the appropriate API scopes are configured for the desired functionalities. Modify the `scopes` dictionary in the module accordingly.

## Disclaimer

This module is a work in progress and may undergo changes and updates. Use with caution in production environments.

## Contributing

Contributions to the Google Calendar Python Module are welcome! If you encounter any issues or have suggestions for improvements, feel free to open an issue or submit a pull request on the GitHub repository.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Author

This module was authored by [Bruno Caracini](https://github.com/brunocaracini).

📅 Schedule, Modify, List and Remove events effortlessly with Google Calendar integration! 🚀
