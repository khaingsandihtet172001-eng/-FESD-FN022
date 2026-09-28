# FESD-FN-022

**66-131216 Front-End Software Development — Final Exam (Lab), 1/2026**
Student: Augusta | ID: 671103022

Angular 17 + Bootstrap 5 web application for the Department of Software
Engineering's online course-registration system.

## Getting started

```bash
npm install
npm start        # ng serve, then open http://localhost:4200
npm test         # ng test, runs the getAge() unit tests (TC-01 to TC-10)
npm run build    # production build
```

## Project structure

```
src/app/
  models/user.model.ts               User class + getAge() (class diagram)
  models/user.model.spec.ts          Unit tests for TC-01..TC-10
  services/user.service.ts           In-memory "backend": register(), 201/400/422/500
  components/user-registration/      Registration form + validation + alerts
  components/user-list/              Responsive table/card user list
```

## How each requirement is covered

| Spec item | Where |
|---|---|
| 3.1 Class-based data model | `models/user.model.ts` |
| 3.1.1 getAge() | `models/user.model.ts` |
| 3.2 Required fields, email pattern, password 8-15, date format | Reactive form validators in `user-registration.component.ts` |
| 4.1 Success alert (201) | Bootstrap alert-success in `user-registration.component.html` |
| 4.2 Error alerts (500/422/400) | Bootstrap alert-danger, messages come from `UserService.register()` |
| 5. Unit tests TC-01..TC-10 | `models/user.model.spec.ts` (`npm test`) |
| 6. User list, responsive, full name concat, dynamic age | `components/user-list/` |

Sample seed data (daranporn@gmail.com, boonpoj@gmail.com) is pre-loaded in
`UserService` so the User List page has content immediately; anything
submitted through the Registration form is added to the same in-memory list.
