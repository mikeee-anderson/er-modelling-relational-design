# Q2 Assumptions — Recruitment Management System

1. `keySkills` is modelled as a multivalued attribute as an applicant may possess more than one skill
2. `workExperience` is omitted as it is considered sufficiently covered by the `resume` attribute
3. `highestQualification` is included as a useful additional attribute per the spec's suggestion
4. `address` on both Applicant and Company is treated as a simple attribute as the system does not require querying by individual address components
5. `applicationStatus` domain is restricted to: submitted, shortlisted, rejected or withdrawn
6. `offerStatus` domain is restricted to: pending, accepted or declined
7. `employmentType` domain is restricted to: full-time, part-time or contract
8. An applicant may have more than one interview for the same position (e.g. an initial interview followed by a final interview)
9. A company can exist in the system before any positions have been advertised
10. An applicant can be registered in the system without having applied for any position yet
11. Company is not directly involved in the Job Offer relationship — the connection to a company is traced indirectly via Position
12. Each position can result in at most one final job offer
13. An interview must always be associated with both an applicant and a position — it cannot exist independently (total participation)
14. A job offer must always be associated with both a position and an applicant — it cannot exist independently (total participation)
15. `interviewMode` domain is restricted to: in-person or online
16. `Interview` is modelled as a strong entity as it has its own `interviewID` and can be uniquely identified without referencing an applicant or position
