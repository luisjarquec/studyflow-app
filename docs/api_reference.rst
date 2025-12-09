API Reference
=============

.. note::
   The StudyFlow API is currently in planning stages. This document describes the planned API 
   structure for future implementation.

Overview
--------

The StudyFlow API will be a RESTful API that allows programmatic access to StudyFlow features. 
It will support creating and managing tasks, boards, reminders, and user data.

Base URL
--------

::

    https://api.studyflow.app/v1

Or for self-hosted instances::

    https://your-domain.com/api/v1

Authentication
--------------

All API requests require authentication using JWT (JSON Web Tokens).

**Obtaining a Token**

POST ``/auth/login``

Request body::

    {
      "email": "user@example.com",
      "password": "your_password"
    }

Response::

    {
      "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...",
      "user": {
        "id": "123",
        "email": "user@example.com",
        "name": "John Doe"
      }
    }

**Using the Token**

Include the token in the Authorization header::

    Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...

Endpoints (Planned)
-------------------

Boards
~~~~~~

**List all boards**

GET ``/boards``

Response::

    {
      "boards": [
        {
          "id": "board_123",
          "name": "CS101 - Data Structures",
          "description": "Course assignments and projects",
          "created_at": "2025-01-15T10:00:00Z",
          "updated_at": "2025-01-20T15:30:00Z"
        }
      ]
    }

**Create a board**

POST ``/boards``

Request body::

    {
      "name": "Math 201",
      "description": "Calculus II assignments",
      "columns": ["To Do", "In Progress", "Done"]
    }

**Get a specific board**

GET ``/boards/{board_id}``

**Update a board**

PUT ``/boards/{board_id}``

**Delete a board**

DELETE ``/boards/{board_id}``

Tasks
~~~~~

**List tasks in a board**

GET ``/boards/{board_id}/tasks``

Query parameters:

* ``status`` - Filter by status (todo, in_progress, done)
* ``priority`` - Filter by priority (high, medium, low)
* ``due_date`` - Filter by due date

**Create a task**

POST ``/boards/{board_id}/tasks``

Request body::

    {
      "title": "Complete Assignment 3",
      "description": "Implement binary search tree",
      "due_date": "2025-02-01T23:59:59Z",
      "priority": "high",
      "tags": ["homework", "coding"],
      "column": "To Do"
    }

**Get a specific task**

GET ``/tasks/{task_id}``

**Update a task**

PUT ``/tasks/{task_id}``

**Delete a task**

DELETE ``/tasks/{task_id}``

**Move a task**

PATCH ``/tasks/{task_id}/move``

Request body::

    {
      "column": "In Progress"
    }

Reminders
~~~~~~~~~

**List reminders**

GET ``/reminders``

**Create a reminder**

POST ``/tasks/{task_id}/reminders``

Request body::

    {
      "type": "email",
      "time": "2025-01-31T09:00:00Z",
      "recurring": false
    }

**Delete a reminder**

DELETE ``/reminders/{reminder_id}``

Users
~~~~~

**Get current user**

GET ``/users/me``

**Update user profile**

PUT ``/users/me``

Request body::

    {
      "name": "Jane Doe",
      "email": "jane@example.com",
      "preferences": {
        "theme": "dark",
        "notifications": true
      }
    }

Analytics
~~~~~~~~~

**Get productivity stats**

GET ``/analytics/productivity``

Query parameters:

* ``start_date`` - Start date for analytics
* ``end_date`` - End date for analytics
* ``board_id`` - Filter by specific board

Response::

    {
      "total_tasks": 45,
      "completed_tasks": 32,
      "completion_rate": 0.71,
      "time_spent": {
        "CS101": 15.5,
        "Math201": 12.3
      }
    }

Response Formats
----------------

Success Response
~~~~~~~~~~~~~~~~

All successful responses follow this format::

    {
      "success": true,
      "data": { ... },
      "message": "Operation completed successfully"
    }

Error Response
~~~~~~~~~~~~~~

All error responses follow this format::

    {
      "success": false,
      "error": {
        "code": "VALIDATION_ERROR",
        "message": "Invalid input data",
        "details": {
          "field": "due_date",
          "issue": "Date must be in the future"
        }
      }
    }

HTTP Status Codes
-----------------

The API uses standard HTTP status codes:

* ``200 OK`` - Request successful
* ``201 Created`` - Resource created successfully
* ``400 Bad Request`` - Invalid request data
* ``401 Unauthorized`` - Authentication required
* ``403 Forbidden`` - Insufficient permissions
* ``404 Not Found`` - Resource not found
* ``429 Too Many Requests`` - Rate limit exceeded
* ``500 Internal Server Error`` - Server error

Rate Limiting
-------------

API requests are rate-limited to prevent abuse:

* **Authenticated users**: 1000 requests per hour
* **Unauthenticated requests**: 100 requests per hour

Rate limit headers are included in all responses::

    X-RateLimit-Limit: 1000
    X-RateLimit-Remaining: 999
    X-RateLimit-Reset: 1640995200

Webhooks (Planned)
------------------

Webhooks will allow you to receive real-time notifications when events occur:

* Task created
* Task updated
* Task completed
* Reminder triggered
* Board shared

Examples
--------

**Creating a Task with cURL**

::

    curl -X POST https://api.studyflow.app/v1/boards/board_123/tasks \
      -H "Authorization: Bearer YOUR_TOKEN" \
      -H "Content-Type: application/json" \
      -d '{
        "title": "Study for midterm",
        "due_date": "2025-02-15T23:59:59Z",
        "priority": "high"
      }'

**Fetching Tasks with JavaScript**

::

    const response = await fetch('https://api.studyflow.app/v1/boards/board_123/tasks', {
      headers: {
        'Authorization': 'Bearer YOUR_TOKEN'
      }
    });
    const data = await response.json();
    console.log(data.tasks);

SDK Support (Future)
--------------------

Official SDKs will be provided for:

* JavaScript/TypeScript
* Python
* Go

Community SDKs may be available for other languages.

Further Information
-------------------

* For implementation updates, see :doc:`release_notes`
* For contributing to API development, see :doc:`contributing`
* Join our `Discord <https://discord.gg/v2ctzYdp>`_ for API discussions
