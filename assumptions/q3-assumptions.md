# Q3 Assumptions — City Library Network

1. A reservation is placed on a Book title, not a specific copy
2. `returnDate` is NULL for loans not yet returned
3. `fineIncurred` is modelled as a derived attribute as it can be determined directly from whether `fineAmount` is null or greater than zero
4. `fineAmount` is NULL for loans where no fine has been incurred
5. A copy cannot be on loan to more than one member at the same time
6. `condition` domain is restricted to: new, good, damaged or lost
7. `availabilityStatus` domain is restricted to: available, on loan, reserved or under repair
8. `reservationStatus` domain is restricted to: pending, fulfilled or cancelled
9. `publisherID` is added as a surrogate primary key for Publisher as `publisherName` alone cannot be guaranteed to be unique in the real world
10. `publisherName` is retained as a regular attribute alongside `publisherID`
11. `bookID` is used as PK rather than ISBN as the spec explicitly provides a unique book ID code
12. A branch can exist in the system before any copies are assigned to it
13. A member can be registered without any active loans
14. Author contact details are modelled as a composite attribute consisting of email and phone and may be null where not available
15. Staff and employment details are excluded as explicitly directed by the spec
16. Book title can exist in the system before any physical copies are acquired
17. Members are linked to copies only through the Loan entity — no direct relationship exists between Member and Copy
18. Reservation is modelled as a strong entity with two binary relationships to Member and Book rather than an M:N relationship or ternary relationship
19. Although `Copy` is existentially dependent on `Book`, it is modelled as a strong entity because `copyID` uniquely identifies it without needing to reference `bookID`. A weak entity requires both existential dependency and the inability to be uniquely identified without the owner's key — Copy only satisfies the first condition
20. `Publisher` is modelled as a strong entity because `publisherID` was added as a surrogate primary key, allowing it to be uniquely identified independently. Despite being closely associated with Books in practice, Publisher is not existentially dependent on Book as a Publisher record can exist in the system before any of its books are catalogued
21. `fullName` on both Member and Author is modelled as a composite attribute consisting of firstName, middleName (optional) and lastName
22. `nationality` on Author is modelled as a multivalued attribute as an author may hold more than one nationality such as in cases of dual citizenship
23. `subjectCategory` on Book is modelled as a multivalued attribute as a single book may belong to multiple subject categories simultaneously
