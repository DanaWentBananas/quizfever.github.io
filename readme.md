# Quiz Fever

System for creating, managing and completing tests with free access.

## Functionality

-   User registration
-   Ability to view and solve other user's tests
-   Various categories
-   Ability to filter by category and search by title
-   Keeping statistics for each user and each test
-   Interactive test editor
-   Fluid UX

## Technologies

-   HTML, CSS, Vanilla JavaScript
-   Lit-html, Page
-   GitHub Pages, Back4app

## Views (Pages)

-   **Landing Page**
-   **Login/Registration** - registration with email, username and password.
-   **Quiz Browser** - list of tests and option to search by title and filter by category.
-   **Quiz Details** - additional description, test statistics, information about the author and option to start the test.
-   **Quiz Contest Mode** - answering questions, each question have separate view, option to skip questions and opportunity to restart the test.
-   **Quiz Results** - summary of the results, option to review the wrong answers.
-   **Profile Page** - information for created and completed tests.
-   **Quiz Editor** - integrated editor for tests, questions and answers.

## Implementation

### Data structure

#### Collections:

(private values are excluded)

-   Sessions
-   Users

```javascript
{
    email: String,
    username: String,
    password: String
}
```

-   Quizzes

```javascript
{
    title: String,
    category: String,
    questionCount: Number
}
```

-   Questions

```javascript
{
    text: String,
    answers: Array<String>,
    answerIndex: Number,
    quiz:  Pointer<Quiz>
}
```

-   Solutions

```javascript
{
    quiz: Pointer<Quiz>,
    correct: Number
}
```

#### Access control

-   Guests can register, see the catalog, see test's details and user profile pages.
-   Registered users can complete tests, view their results, create and edit tests.
-   Only the creator of a test can edit and delete it.
-   Each registered user can solve other user's tests.
