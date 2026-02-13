# ReminderApp
## Introduction
Many students have personal, work, and school calendars scattered across different online platforms. This makes it hard to manage their time effectively and keep track of their weekly schedules, and they can't be everywhere at once. Students may forget homework, run out of time to study, and save everything for the last minute as they don't have proper resources to view and manage their tasks and events. This is Studious, a web app that accepts keys from various calendar sources and merges them into one interface. Has support for Canvas, Google Calendar, Blackboard, and more. It will cohesively collect all upcoming events from each imported calendar and display them with working links, times, dates, and information. Users will be able to edit, add, or delete events as needed. Upcoming events will send the user a notification (text or email based on user settings) so they have consistent reminders for their obligations. These reminders can be changed in settings to be sent at certain intervals such as one day before, 10 minutes before, and so on. 

## Storyboard
![ReminderAppStoryBoard](https://github.com/user-attachments/assets/f0594e1e-e9bb-4af3-8125-f2172eb89d6e)

## Functional Requirements

## Class Diagram
classDiagram
    class User {
        +int UserID
        +string Email
        +string Preferences
        +Login()
        +UpdateSettings()
    }

    class Event {
        +string Title
        +DateTime StartTime
        +DateTime EndTime
        +string Link
        +Create()
        +Edit()
        +Delete()
    }

    class CalendarManager {
        +List~Event~ AllEvents
        +MergeCalendars()
        +GetUpcomingEvents()
    }

    class ICalendarProvider {
        <<interface>>
        +Connect()
        +FetchEvents()
    }

    class GoogleCalendar {
        +ApiKey string
        +FetchEvents()
    }

    class CanvasCalendar {
        +ApiKey string
        +FetchEvents()
    }

    class AIChatbot {
        +string CurrentContext
        +SendMessage(string prompt)
        +UploadFile(File resource)
        +GenerateStudyPlan()
    }

    class LLMService {
        +string APIKey
        +SendRequest()
        +ParseResponse()
    }

    class NotificationSystem {
        +SendEmail()
        +SendSMS()
        +ScheduleReminder()
    }

    class DatabaseContext {
        +SaveUserKeys()
        +RetrieveUserKeys()
    }

    %% Relationships
    User "1" --> "1" CalendarManager : Uses
    User "1" --> "1" AIChatbot : Interacts with
    CalendarManager "1" --> "*" Event : Manages
    CalendarManager "1" --> "*" ICalendarProvider : Aggregates
    ICalendarProvider <|.. GoogleCalendar : Implements
    ICalendarProvider <|.. CanvasCalendar : Implements
    AIChatbot ..> CalendarManager : Reads/Modifies
    AIChatbot --> LLMService : Uses
    CalendarManager ..> NotificationSystem : Triggers
    CalendarManager --> DatabaseContext : Persists Data
## JSON Schema

## Members and Roles
Shah Opal - Product Owner \
Chris Vu - Scrum Master \
Rohit Vijai - Developer \
Jacob Dice - Developer 
## Kanban Board
To stay up to date on current development and tasks, please refer to the Projects tab of Github!
