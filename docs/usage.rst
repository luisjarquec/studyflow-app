How to Use StudyFlow
====================

This guide will help you understand how to use StudyFlow effectively for managing your academic life.

.. note::
   StudyFlow is currently in early development (v0.0.1). This guide describes planned features 
   and current functionality.

Current Features
----------------

Jekyll Website
~~~~~~~~~~~~~~

The StudyFlow website is currently available and provides information about the project:

**Viewing the Website**

Visit the live website or run it locally::

    cd website
    bundle exec jekyll serve

Navigate to ``http://localhost:4000`` to explore:

* **Home Page** - Overview of StudyFlow and its mission
* **Features Page** - Detailed feature showcase
* **Community Page** - Links to Discord, GitHub Discussions, and Google Group
* **Contact Page** - Ways to get in touch with the team

Planned Features (Coming Soon)
-------------------------------

The following features are planned for the StudyFlow application:

Managing Kanban Boards
~~~~~~~~~~~~~~~~~~~~~~~

**Creating a Board**

1. Create a new board for each course or project
2. Name your board (e.g., "CS101 - Data Structures")
3. Customize columns (To Do, In Progress, Done, etc.)

**Adding Tasks**

1. Click "Add Task" in any column
2. Enter task details:
   
   * Title (e.g., "Complete Assignment 3")
   * Description
   * Due date
   * Priority level
   * Attach resources (PDFs, links, notes)

3. Drag and drop tasks between columns as you progress

**Organizing Tasks**

* Use labels to categorize tasks (Homework, Exam, Reading, Project)
* Set priority levels (High, Medium, Low)
* Add tags for easy filtering
* Archive completed tasks

Setting Up Smart Reminders
~~~~~~~~~~~~~~~~~~~~~~~~~~~

**Creating Reminders**

1. Open any task
2. Click "Add Reminder"
3. Choose reminder timing:
   
   * 1 day before deadline
   * 1 week before deadline
   * Custom time
   * Recurring reminders

4. Select notification method:
   
   * In-app notifications
   * Email notifications
   * Browser notifications

**Managing Notifications**

* View all upcoming reminders in the Notifications panel
* Snooze reminders if needed
* Mark reminders as complete
* Customize notification preferences in Settings

Tracking Your Progress
~~~~~~~~~~~~~~~~~~~~~~~

**Viewing Analytics**

Access the Progress Dashboard to see:

* **Time Spent** - Hours dedicated to each course
* **Completion Rate** - Percentage of tasks completed on time
* **Productivity Trends** - Daily/weekly productivity graphs
* **Subject Breakdown** - Time distribution across courses

**Generating Reports**

* Weekly summary of completed tasks
* Monthly productivity reports
* Semester overview
* Export data as CSV or PDF

Collaborating on Group Projects
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

**Creating Shared Boards**

1. Create a new board
2. Click "Share Board"
3. Invite team members by email or username
4. Set permissions (View, Edit, Admin)

**Working Together**

* Add comments to tasks for discussion
* Mention team members with @username
* Track who's working on what
* View activity log for all changes
* Real-time updates when team members make changes

Managing Resources
~~~~~~~~~~~~~~~~~~

**Attaching Files**

* Upload PDFs, images, or documents to any task
* Attach links to online resources
* Add notes and study materials
* Organize files in folders

**Accessing Resources**

* Quick search across all attached resources
* Filter by file type or course
* Download files for offline access
* Share resources with team members

Using the Calendar View
~~~~~~~~~~~~~~~~~~~~~~~~

**Calendar Features**

* View all deadlines in monthly/weekly calendar
* Color-code by course or priority
* Sync with Google Calendar, Outlook, or iCal
* Set recurring events for classes
* Block study time on your calendar

**Managing Deadlines**

* See upcoming deadlines at a glance
* Filter by course or project
* Reschedule tasks by dragging in calendar
* Set buffer time before major deadlines

Customization
-------------

Dark Mode
~~~~~~~~~

Toggle between light and dark themes:

1. Click your profile icon
2. Select "Appearance"
3. Choose Light, Dark, or Auto (based on system settings)

Privacy Settings
~~~~~~~~~~~~~~~~

**Self-Hosting**

For maximum privacy, self-host StudyFlow:

1. Follow the :doc:`getting_started` guide
2. Deploy to your own server
3. Configure database settings
4. Set up backups

**Data Control**

* Export all your data at any time
* Delete your account and all associated data
* Control what data is stored
* No third-party tracking or analytics

Tips for Success
-----------------

Best Practices
~~~~~~~~~~~~~~

* **Review daily** - Check your boards every morning
* **Plan weekly** - Set up tasks for the upcoming week every Sunday
* **Use labels** - Categorize tasks for easy filtering
* **Set realistic deadlines** - Give yourself buffer time
* **Archive regularly** - Keep your boards clean and focused

Keyboard Shortcuts
~~~~~~~~~~~~~~~~~~

Speed up your workflow with keyboard shortcuts (coming soon):

* ``Ctrl+N`` - New task
* ``Ctrl+K`` - Quick search
* ``Ctrl+/`` - Show all shortcuts
* ``Esc`` - Close modal
* Arrow keys - Navigate between tasks

Getting Help
------------

If you need assistance:

* Check the :doc:`faq` for common questions
* Join our `Discord server <https://discord.gg/v2ctzYdp>`_ for real-time help
* Ask on `GitHub Discussions <https://github.com/luisjarquec/studyflow-app/discussions>`_
* Report bugs on `GitHub Issues <https://github.com/luisjarquec/studyflow-app/issues>`_

Next Steps
----------

* Explore the :doc:`technical_overview` to understand how StudyFlow works
* Read the :doc:`configuration` guide to customize your setup
* Check :doc:`contributing` to help build StudyFlow
