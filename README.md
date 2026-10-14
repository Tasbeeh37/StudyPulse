StudyPulse
Individual App Project — IT8101— Final Submission Document
Name: Tasbeeh Saeed Yousef ALsubh
ID: 202305409
Section: 001
Tuter: Dr.Ghassan
________________________________________
1. App Identity
	
Name	StudyPulse
Category	Study & Habit Tracker
Tech Stack	Swift & SwiftUI 

2. The Problem
Students often start with good intentions — a study plan, reading goals, upcoming deadlines — but lose momentum because there's no single place to see daily habits, study notes, and important dates together, with visible progress to stay motivated.
3. The Solution
StudyPulse combines four things in one consistently-branded app: daily habit tracking with live progress visualization, study notes with category filtering, a calendar for assessments/meetings/deadlines/projects, and a lightweight personalized profile.
4. Screens (4 tabs)/ Features
1.	Today — greeting (personalized if logged in), daily target card with live progress bar and streak, add/toggle/delete habits
2.	Progress — circular progress ring, habits-done count, current streak — all reading the same live data as Today
3.	Notes — add study notes/reminders, filter by category (Goals, Deadlines, Key Concepts), toggle/delete
4.	Calendar — add assessments/meetings/deadlines/projects with a type picker and date picker, list sorted chronologically, delete
Plus, a Profile sheet (accessible from every screen) for a lightweight login/logout session.
5. What Makes It Unique
•	One shared @Observable model (StudyPulseModel) driving all four screens — a cleaner, more advanced architecture than keeping state separately per screen
•	Consistent custom brand identity — a single Color.burgundy defined once, reused everywhere, instead of default system styling
•	Genuinely reactive streak — increments for real the moment all habits are completed, not a decorative fixed number
•	Adaptive empty states — friendly messages instead of blank screens, with wording that distinguishes "nothing added yet" from "nothing matches this filter"
•	Full interactivity everywhere — every list supports add, toggle, and delete; nothing is read-only decoration
6. Programming Concepts Demonstrated
Concept	Where
Structs & Identifiable	HabitItem, StudyNoteItem, CalendarEvent
Enums	NoteTagType, EventType
@Observable shared state	StudyPulseModel
Computed properties	completionPercentage, filteredNotes, sortedEvents
guard statements	Input validation in every add...() function
Functions	10+ clearly named, single-purpose functions
Date & sorting	CalendarEvent.date, .sorted { $0.date < $1.date }
Conditional UI	Login/logout states, empty states, filter highlighting
Built-in controls	TextField, Picker, DatePicker, ProgressView

8. Honest Notes The login system is a local session demo — no password, no backend, no persisted account storage.
•	The streak resets its "already counted today" flag when a habit is un-completed, so within one sitting it's possible to re-trigger it. A production version would track this per real calendar day, which needs data persistence beyond this course's current scope.
•	Calendar events don't persist between app launches (no saved storage) — same scope reason as above.

