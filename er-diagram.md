```mermaid
erDiagram
          User ||--|| Calendar: has
          Calendar ||--|{ Event: has
          User }|--|{ Role: has
          Issue }|--|| Task: contains
          Issue ||--|| User: has
          Issue ||--|{ Solution: has
          Task ||--o{ Tag: has
          Task ||--|{ Test: has
          Solution ||--|{ Check: has
          Solution ||--|{ Snippet: has
          Solution ||--|| Verdict: has
          Check }|--|| Test: has
          Course ||--|{ Lesson: has
          Course ||--o{ Project: has
          Course ||--|{ Howto: has
          Classroom }|--|| Tenant: has
          Classroom ||--|{ Feedback: has
          Classroom ||--|{ Note: has
          Classroom ||--|{ Chat: has
          Classroom ||--|{ Course: has
          Classroom || -- |{ Progress: has
          Lesson ||--|{ Proposal: has
          Lesson ||--|| Presentation: has
          Presentation ||--|{ Slide: has
          Slide ||--|| Document: has
          Slide ||--|| Video: has
          Slide ||--|| Task: has
          Issue ||--o| Prize: has
          Project ||--|{ Document: contains
          Project ||--|{ Repo: contains
          Proposal ||--|| Document: has
          Slide ||--|| Question: has
          Question ||--|| Answer: has
          Question ||--|{ Variant: has
          User ||--|{ Achievement: has
          User ||--|| Resume: has
          Calendar {
            Name string
          }
          Event {
            Name string
            CalendarId uint64
            Schedule Schedule
          }
          User {
            ProfileId uint64
            CalendarId uint64
          }
          Tag {
            Type string
            Value string
          }
          Resume {
            UserId uint64
            DocumentId uint64
          }
          Achievement {
            Name string
            Description string
          }
          Slide {
            LessonId uint64
            Number uint64
          }
          Role {
            Service string
            Operation string
          }
          Howto {
            CourseId uint64
            Question string
            Answer string
          }
          Question {
            Text string
          }
          Repo {
            ProjectId uint64
            UserId uint64
            Link string
          }
          Answer {
            QuestionId uint64
            UserId uint64
            Success bool
          }
          Variant {
            QuestionId uint64
            Text string
            Success bool
          }
          Progress {
            ClassroomId uint64
            PresentationId uint64
            SlideId uint64
            UserId uint64
          }
          Presentation {
            Name string
            LessonId uint64
          }
          Verdict {
            SolutionId uint64
            Comment string
            Status enum
            Timestamp int64
          }
          Check {
            SolutionId uint64
            TestId uint64
            RunnerId uint64
            Success bool
          }
          Runner {
            Guid string
            Os string
            Arch string
          }
          Video {
            Link string
          }
          Chat {
            ClassroomId uint64
            Link string
          }
          Course {
            ClassroomId uint64
            Name string
            Stream string
          }
          Project {
            CourseId uint64
            Name string
          }
          Feedback {
            ClassroomId uint64
            UserId  uint64
            Comment string
          }
          Document {
            Link string
          }
          Note {
            UserId uint64
            ClassroomId uint64
            DocumentId uint64
          }
          Lesson {
            Number uint64
            Name string
          }
          Classroom {
            TenantId uint64
            CalendarId uint64
          }
          Tenant {
            Name string
            Type uint
          }
          Issue {
            ClassroomId uint64
            UserId uint64
            TaskId uint64
            Dealine Time
          }
          Solution {
            IssueId uint64
          }
          Task {
            IssueId uint64
            Difficulty enum
          }
          Test {
            TaskId uint64
            Input string
            Output string
          }
          Proposal {
            LessonId uint64
            UserId uint64
            DocumentId uint64
          }
          Prize {
            IssueId uint64
            Link     string
          }
          Snippet {
            SolutionId uint64
            UserId uint64
            Text string
            Language string
          }
```
