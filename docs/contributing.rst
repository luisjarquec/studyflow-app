Contribution Guidelines
=======================

We welcome contributions to the StudyFlow App! By participating in this project, you agree to 
abide by our `Code of Conduct <https://github.com/luisjarquec/studyflow-app/blob/main/CODE_OF_CONDUCT.md>`_.

How Can I Contribute?
---------------------

Reporting Bugs
~~~~~~~~~~~~~~

If you find a bug, please open an issue on our `GitHub repository 
<https://github.com/luisjarquec/studyflow-app/issues>`_. Before opening a new issue, please check 
if a similar issue already exists.

When reporting a bug, please include:

* A clear and concise description of the bug
* Steps to reproduce the behavior
* Expected behavior
* Screenshots or error messages if applicable
* Your operating system and browser (if applicable)

Suggesting Enhancements
~~~~~~~~~~~~~~~~~~~~~~~

We love new ideas! If you have a suggestion for a new feature or an improvement to an existing 
one, please open an issue on our GitHub repository. Describe your idea clearly and explain why 
you think it would be a valuable addition.

Submitting Pull Requests
~~~~~~~~~~~~~~~~~~~~~~~~~

1. **Fork the repository** and clone it to your local machine
2. **Create a new branch** for your feature or bug fix: ``git checkout -b feature/your-feature-name``
3. **Make your changes** - Ensure your code adheres to the project's coding style
4. **Write tests** for your changes if applicable
5. **Run tests** to ensure everything is working correctly
6. **Commit your changes** with a clear and descriptive commit message
7. **Push your branch** to your forked repository
8. **Open a Pull Request** to the ``main`` branch of the original repository

Development Setup
-----------------

See our :doc:`getting_started` guide for detailed setup instructions.

Quick setup for the Jekyll website::

    cd website
    gem install jekyll bundler
    bundle install
    bundle exec jekyll serve

Coding Style Guidelines
-----------------------

* Use clear, descriptive variable and function names
* Keep functions small and focused on a single responsibility
* Add comments for complex logic
* Follow the existing code style in the repository
* Ensure your code passes all linting checks before submitting a PR

Commit Message Guidelines
--------------------------

We follow the Conventional Commits specification::

    <type>(<scope>): <description>

**Type examples:** ``feat``, ``fix``, ``docs``, ``style``, ``refactor``, ``test``, ``chore``

**Scope examples:** ``website``, ``docs``, ``ui``, ``config``, ``build``, ``deps``

**Examples:**

* ``feat(website): Add features page with Kanban board showcase``
* ``fix(website): Correct navigation links in mobile view``
* ``docs(readme): Update installation instructions``
* ``chore(deps): Update Jekyll to v4.3.0``

Community
---------

Join our community:

* `Discord Server <https://discord.gg/v2ctzYdp>`_ - Real-time chat and collaboration
* `GitHub Discussions <https://github.com/luisjarquec/studyflow-app/discussions>`_ - Ask questions and share ideas
* `Google Group <https://groups.google.com/g/study-flow-app>`_ - Announcements and updates

For More Details
----------------

Please see the complete `CONTRIBUTING.md 
<https://github.com/luisjarquec/studyflow-app/blob/main/CONTRIBUTING.md>`_ file in our repository 
for comprehensive contribution guidelines.

Thank you for contributing to StudyFlow! 🎓
