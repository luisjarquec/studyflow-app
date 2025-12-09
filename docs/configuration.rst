Configuration Guide
===================

This guide covers configuration options for the StudyFlow Jekyll website and planned application.

Jekyll Website Configuration
-----------------------------

The Jekyll website is configured via ``website/_config.yml``.

Basic Settings
~~~~~~~~~~~~~~

::

    title: StudyFlow
    description: Organize your study workflow efficiently.
    baseurl: ""  # Leave empty for root domain
    url: ""      # Your site URL

Navigation
~~~~~~~~~~

Customize the navigation menu in ``_config.yml``::

    navigation:
      - title: Home
        url: /
      - title: Features
        url: /features/
      - title: Community
        url: /community/
      - title: Contact
        url: /contact/
      - title: Docs
        url: https://studyflow-app.readthedocs.io/

Theme Customization
~~~~~~~~~~~~~~~~~~~

Custom CSS is located in ``website/assets/css/style.css``.

Key variables you can modify:

* Colors and gradients
* Font families
* Spacing and layout
* Dark mode styles

Plugins
~~~~~~~

Currently enabled Jekyll plugins::

    plugins:
      - jekyll-feed
      - jekyll-seo-tag

Sphinx Documentation Configuration
-----------------------------------

Documentation is configured via ``docs/conf.py``.

Project Information
~~~~~~~~~~~~~~~~~~~

::

    project = 'StudyFlow App'
    copyright = '2025, StudyFlow Contributors'
    author = 'StudyFlow Contributors'

Theme Settings
~~~~~~~~~~~~~~

::

    html_theme = 'sphinx_rtd_theme'
    html_theme_options = {
        'navigation_depth': 4,
        'collapse_navigation': False,
    }

Extensions
~~~~~~~~~~

Enabled Sphinx extensions::

    extensions = [
        'sphinx.ext.autodoc',
        'sphinx.ext.viewcode',
    ]

Future Application Configuration
---------------------------------

Environment Variables
~~~~~~~~~~~~~~~~~~~~~

The application will use environment variables for configuration.

Create a ``.env`` file::

    # Database
    DATABASE_URL=postgresql://user:password@localhost:5432/studyflow
    
    # Authentication
    JWT_SECRET=your-secret-key-here
    JWT_EXPIRATION=7d
    
    # Server
    PORT=3000
    NODE_ENV=development
    
    # Email (for notifications)
    SMTP_HOST=smtp.example.com
    SMTP_PORT=587
    SMTP_USER=your-email@example.com
    SMTP_PASS=your-password

Application Settings
~~~~~~~~~~~~~~~~~~~~

Configuration file (``config/default.json``)::

    {
      "app": {
        "name": "StudyFlow",
        "version": "0.0.1"
      },
      "features": {
        "reminders": true,
        "collaboration": true,
        "analytics": true
      },
      "limits": {
        "maxBoardsPerUser": 50,
        "maxTasksPerBoard": 1000,
        "maxFileSize": 10485760
      }
    }

Database Configuration
~~~~~~~~~~~~~~~~~~~~~~

PostgreSQL connection settings::

    {
      "database": {
        "host": "localhost",
        "port": 5432,
        "name": "studyflow",
        "pool": {
          "min": 2,
          "max": 10
        }
      }
    }

Security Settings
~~~~~~~~~~~~~~~~~

CORS configuration::

    {
      "cors": {
        "origin": ["http://localhost:3000"],
        "credentials": true
      }
    }

Rate limiting::

    {
      "rateLimit": {
        "windowMs": 900000,
        "max": 100
      }
    }

Deployment Configuration
------------------------

GitHub Pages (Jekyll)
~~~~~~~~~~~~~~~~~~~~~

1. Enable GitHub Pages in repository settings
2. Set source to ``website`` directory or use GitHub Actions
3. Custom domain (optional): Add ``CNAME`` file to ``website/``

ReadTheDocs
~~~~~~~~~~~

1. Connect your GitHub repository
2. Configure build settings in ``.readthedocs.yaml``
3. Documentation builds automatically on push

Self-Hosting (Future)
~~~~~~~~~~~~~~~~~~~~~

**Using Docker**::

    docker-compose up -d

**Using PM2**::

    pm2 start npm --name "studyflow" -- start

**Using systemd**::

    sudo systemctl start studyflow
    sudo systemctl enable studyflow

Customization Tips
------------------

Colors and Branding
~~~~~~~~~~~~~~~~~~~

Update the color scheme in ``website/assets/css/style.css``::

    :root {
      --primary-color: #3b82f6;
      --secondary-color: #8b5cf6;
      --background: #0f172a;
    }

Notifications
~~~~~~~~~~~~~

Configure notification preferences (future)::

    {
      "notifications": {
        "email": true,
        "push": true,
        "reminderDefaults": {
          "enabled": true,
          "timing": "1d"
        }
      }
    }

Backup Settings
~~~~~~~~~~~~~~~

Configure automatic backups (future)::

    {
      "backup": {
        "enabled": true,
        "schedule": "0 2 * * *",
        "retention": 30
      }
    }

Further Reading
---------------

* :doc:`getting_started` - Setup instructions
* :doc:`maintenance` - Maintenance and troubleshooting
* :doc:`technical_overview` - Technical architecture
