@startuml
actor User
participant "Online Movie Ticket Platform" as System
database MovieDatabase
User -> System: Search for movie by title
System -> MovieDatabase: Search for matching movies
MovieDatabase -> System: Return list of matching movies
System -> User: Display list of matching movies
User -> System: Select a movie
System -> MovieDatabase: Retrieve movie details and showtimes
MovieDatabase -> System: Return movie details and showtimes
System -> User: Display movie details and available showtimes
User -> System: Select a showtime
System -> MovieDatabase: Check seat availability
MovieDatabase -> System: Return seat availability
System -> User: Display available seats
User -> System: Choose seats
System -> MovieDatabase: Create reservation
MovieDatabase -> System: Confirm reservation created
System -> User: Proceed to checkout
User -> System: Complete payment
System -> MovieDatabase: Update reservation status
System -> User: Display confirmation of reservation and payment
@enduml