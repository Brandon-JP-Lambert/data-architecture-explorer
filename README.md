# data-architecture-explorer

This repository contains a series of prompt templates designed to help you design the data architecture of various platforms using Generative AI tools like ChatGPT and then create dummy data in Python to experiment with. The prompts guide you through designing the database, writing mermaid.js syntax, improving the design, and generating contextually appropriate dummy data for the platform.

## Prompt Templates

**Prompt 1:**

```
Write Mermaid syntax for an ER diagram for [database].
```
Replace `[database]` with the desired platform or project for which you want to create an ER diagram.

**Prompt 2:**

```
Improve this as a [role].
```
Replace `[role]` with your expertise, such as "senior data scientist" or "database architect", to refine and optimize the initial database design.

**Prompt 3:**
```
Write a Python program that generates [number] [entities] and dummy data based on the ER diagram. Use the OpenAI API to build prompts into the code that creates random but contextually appropriate content. Write the script to ensure that prompts don't produce very similar results.
```
Replace `[number]` with the desired number of entities and `[entities]` with the type of entities (e.g., learners, users, products) for which you want to generate dummy data.

## Sample Prompts

### Online Learning Platform

**Sample Prompt 1:**

```
Write Mermaid syntax for an ER diagram for an online learning platform's database.
```

**Sample Output 1:**

```
erDiagram
    USERS ||..|| ENROLLMENTS : has
    USERS ||--|| SUBMISSIONS : submits
    COURSES ||--|| LESSONS : contains
    COURSES ||..|| ENROLLMENTS : has
    LESSONS ||--|| ASSESSMENTS : includes
    ASSESSMENTS ||--|| SUBMISSIONS : receives

    USERS {
        int id
        string email
        string password
        string firstName
        string lastName
        string userType
    }

    COURSES {
        int id
        string title
        string description
        string category
        int creatorId
    }

    LESSONS {
        int id
        string title
        string content
        int courseId
    }

    ENROLLMENTS {
        int id
        int userId
        int courseId
        date enrolledAt
    }

    ASSESSMENTS {
        int id
        string type
        string question
        string correctAnswer
        int lessonId
    }

    SUBMISSIONS {
        int id
        int userId
        int assessmentId
        string userAnswer
        bool isCorrect
        date submittedAt
    }
```

[View on Kroki](https://kroki.io/mermaid/svg/eNqdU1FuwjAM_ecUuQAcYH-M9aMSFInAAULjMUtpAo47hNbdfem6oqSUoc1fjf3y_PziAr2gOpCqJiLETmYbKZpmNmsakRWb9XK5yoqtFE_iTfkEMp0GiNw9r3Ip83XRQny9r5A72GK928jsClxmUnag0llWaIeoXzr2d3-o5jLckD0IbWlqDR0yLo0qJCgB3wM6GuXj-7sNtCxQX4-eCe1BQKXQDJNH5f3Z0Q34FclzoSoYFowaz9ceaHs5dvnPSeLKI2WMbG4Igxcl4ZHR2WGpVAwHR5eEtiRQ7CjXsYLe8n8paF8YLKddXE0e0ibxa99t1B5bj3J9n68NHWYTYMkZA3rOcZ94Kx4O1D9FlDvV4EftdBT2iefWn4ESXgPeO5tOGy_iX6cNyxYYq2BqrscWaCBh75wR6BedvtSi7h_lyKMvO20YYQ)

**Sample Prompt 2:**

```
Improve this as a senior edtech data scientist.
```

**Sample Output 2:**

```
erDiagram
    USERS ||..|| ENROLLMENTS : has
    USERS ||--|| SUBMISSIONS : submits
    USERS ||--|| FORUM_POSTS : posts
    USERS ||--|{ INSTRUCTORS : is_a
    COURSES ||--|| LESSONS : contains
    COURSES ||..|| ENROLLMENTS : has
    COURSES ||..|{ COURSE_CATEGORIES : belongs_to
    COURSES ||..|| INSTRUCTORS : taught_by
    COURSES ||--|| DISCUSSION_FORUMS : has
    LESSONS ||--|| ASSESSMENTS : includes
    LESSONS ||..|| COURSE_PROGRESS : tracks
    ASSESSMENTS ||--|| SUBMISSIONS : receives
    DISCUSSION_FORUMS ||--|| FORUM_POSTS : contains

    USERS {
        int id
        string email
        string password
        string firstName
        string lastName
        string userType
    }

    INSTRUCTORS {
        int userId
        string bio
        string expertise
    }

    COURSE_CATEGORIES {
        int id
        string name
        string description
    }

    COURSES {
        int id
        string title
        string description
        int categoryId
        int instructorId
    }

    LESSONS {
        int id
        string title
        string content
        int courseId
    }

    ENROLLMENTS {
        int id
        int userId
        int courseId
        date enrolledAt
    }

    COURSE_PROGRESS {
        int id
        int userId
        int lessonId
        bool completed
        date lastAccessed
    }

    ASSESSMENTS {
        int id
        string type
        string question
        string correctAnswer
        int lessonId
    }

    SUBMISSIONS {
        int id
        int userId
        int assessmentId
        string userAnswer
        bool isCorrect
        date submittedAt
    }

    DISCUSSION_FORUMS {
        int id
        int courseId
        string title
    }

    FORUM_POSTS {
        int id
        int userId
        int forumId
        string content
        date postedAt
    }
```

[View on Kroki](https://kroki.io/mermaid/svg/eNqdVdtunDAQfe9X8APJB_SNEhoh7UKE4RkZdkKsGJvapulqt_9em5tsTLLa-gnM8Zkzc2YMiCeCW4G7b4FeJYpzFFyvj4_XaxCneXY4HOO0QMH34A1LB_LwoCGo_HFMEEqy1EDkUHdE7cB-Znl5rF4yNDL1XPqgS5CkqMjLqMhyAyKywiMmysocxSvVIUZoitZwpjBhcoP6QroDusyvVRQW8XOWJ7GB1kA5a2Wl-B6tK1HhoX1TVX3e0_mUoKgcK1ON2ds6lhxmaIj0ObSIJayhwwm2yDH-rPglz55z_cVoELh5n7A2za49Ahogv2dmX9-uV2uRLb8u47NZhKmAnNZXqQRhbQAdJnS72WMpP7jwwK9ESJXiDrYfKN7fHySI4txP-38nXbYvrjqDTrygNeGe6D89CEWkw-t3yK3c2Y5ibWYjSK8IZz75bUpFFL3JuRxvsIKWi7OV88jK9LmhUXwpxqxh6a__0mB6A5hy4_NBSHCD2MP4aaAdszw-s046wQCY4JTCKVQ7bq3TcW8sClJyZm3WnFOtoOspKNhIMO0ZNo0-Ak6y9hTerOrSxtberwGk4-pabKHnV4VMfoD4XPaswh78e8ugB1UzdtpZf3AMfCNhLBKR0aTPLdL0Q1Bbo_y750uNXg94TTnz2lfXvVm_cjF0foxtj49pmR-YldM_Ehf7Ww)

**Sample Prompt 3:**

```
Write a python program that generates approximately 100 learners and dummy data based on the ER diagram. Use the OpenAI API to build prompts into the code that creates random but contextually appropriate content. Write the script to ensure that prompts don't produce very similar results.
```

**Sample Output 3:**

Here is a sample output for the script:

Users:
{'id': 1, 'email': 'johnsonmelissa@gmail.com', 'password': 'tR4y%gk2', 'firstName': 'Melissa', 'lastName': 'Johnson', 'userType': 'learner'}
{'id': 2, 'email': 'sarah94@example.com', 'password': 'Z7^3wnNq', 'firstName': 'Sarah', 'lastName': 'Smith', 'userType': 'learner'}
... (omitted for brevity)

Course Categories:
{'id': 1, 'name': 'Optimized heuristic infrastructure', 'description': 'Incididunt veniam officia aliquip...'}
{'id': 2, 'name': 'Reactive uniform flexibility', 'description': 'Elit minim ut tempor...'}
... (omitted for brevity)

Courses:
{'id': 1, 'title': 'Mastering Web Development', 'description': 'Learn the fundamentals of web...', 'categoryId': 2, 'instructorId': 43}
{'id': 2, 'title': 'Intro to Python Programming', 'description': 'Discover the basics of Python...', 'categoryId': 4, 'instructorId': 27}
... (omitted for brevity)

Lessons:
{'id': 1, 'title': 'HTML Basics', 'content': 'HTML stands for Hyper Text...', 'courseId': 1}
{'id': 2, 'title': 'Python Variables and Data Types', 'content': 'In this lesson, we will...', 'courseId': 2}
... (omitted for brevity)

Enrollments:
{'id': 1, 'userId': 67, 'courseId': 6, 'enrolledAt': '2021-08-15'}
{'id': 2, 'userId': 12, 'courseId': 14, 'enrolledAt': '2021-04-23'}
... (omitted for brevity)

Assessments:
{'id': 1, 'type': 'multiple_choice', 'question': 'Which of the following is a...', 'correctAnswer': 'paragraph', 'lessonId': 1}
{'id': 2, 'type': 'true_false', 'question': 'Python is a case-sensitive...', 'correctAnswer': 'True', 'lessonId': 2}
... (omitted for brevity)

Submissions:
{'id': 1, 'userId': 54, 'assessmentId': 1, 'userAnswer': 'section', 'isCorrect': False, 'submittedAt': '2021-12-07'}
{'id': 2, 'userId': 29, 'assessmentId': 2, 'userAnswer': 'True', 'isCorrect': True, 'submittedAt': '2021-03-15'}
... (omitted for brevity)

Discussion Forums:
{'id': 1, 'courseId': 1, 'title': 'HTML and CSS Help'}
{'id': 2, 'courseId': 2, 'title': 'Python Troubleshooting'}
... (omitted for brevity)

Forum Posts:
{'id': 1, 'userId': 17, 'forumId': 1, 'content': 'Can anyone help me with...', 'postedAt': '2021-05-20'}
{'id': 2, 'userId': 42, 'forumId': 2, 'content': 'How do I create a list in...', 'postedAt': '2021-07-14'}
... (omitted for brevity

## Usage

This tool is designed to be used with generative text tools like ChatGPT. Simply edit the prompts with your requirements, and the prompt will generate the Mermaid syntax for the ER diagram and Python code for dummy data.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.
