Maintenance and Troubleshooting
===============================

This guide covers common issues, maintenance tasks, and troubleshooting for StudyFlow.

Jekyll Website Issues
---------------------

Jekyll Won't Start
~~~~~~~~~~~~~~~~~~

**Problem**: ``jekyll serve`` fails to start

**Solutions**:

1. Check Ruby version::

    ruby --version  # Should be 2.7+

2. Reinstall dependencies::

    bundle install

3. Clear Jekyll cache::

    bundle exec jekyll clean
    bundle exec jekyll serve

Bundler Errors
~~~~~~~~~~~~~~

**Problem**: ``bundle install`` fails

**Solutions**:

1. Update Bundler::

    gem install bundler

2. Remove Gemfile.lock and reinstall::

    rm Gemfile.lock
    bundle install

Port Already in Use
~~~~~~~~~~~~~~~~~~~

**Problem**: Port 4000 is already in use

**Solution**: Use a different port::

    bundle exec jekyll serve --port 4001

Documentation Build Issues
--------------------------

Sphinx Build Fails
~~~~~~~~~~~~~~~~~~

**Problem**: ``make html`` fails

**Solutions**:

1. Install/update Sphinx::

    pip install -U sphinx sphinx_rtd_theme

2. Check for syntax errors in .rst files

3. Clean build directory::

    cd docs
    rm -rf _build
    make html

Missing Dependencies
~~~~~~~~~~~~~~~~~~~~

**Problem**: Import errors during build

**Solution**: Install requirements::

    cd docs
    pip install -r requirements.txt

Git and GitHub Issues
---------------------

Merge Conflicts
~~~~~~~~~~~~~~~

**Problem**: Merge conflicts when pulling changes

**Solutions**:

1. Stash your changes::

    git stash
    git pull
    git stash pop

2. Or resolve conflicts manually::

    git pull
    # Edit conflicted files
    git add .
    git commit -m "Resolve merge conflicts"

Large Files
~~~~~~~~~~~

**Problem**: Can't push large files

**Solution**: Use Git LFS or add to .gitignore::

    echo "large-file.pdf" >> .gitignore
    git rm --cached large-file.pdf

Regular Maintenance Tasks
-------------------------

Daily
~~~~~

* Monitor error logs
* Check system resources (CPU, memory, disk)
* Review user-reported issues

Weekly
~~~~~~

* Update dependencies::

    bundle update  # Jekyll
    npm update     # Node.js (future)

* Review and merge pull requests
* Check for security updates

Monthly
~~~~~~~

* Database backup verification (future)
* Performance review and optimization
* Documentation updates
* Community engagement (Discord, GitHub)

Quarterly
~~~~~~~~~

* Major dependency updates
* Security audit
* User feedback review
* Roadmap planning

Backup and Recovery
-------------------

Backing Up Jekyll Site
~~~~~~~~~~~~~~~~~~~~~~

The Jekyll site is in Git, so regular commits serve as backups::

    git add .
    git commit -m "Backup: $(date)"
    git push

Backing Up Documentation
~~~~~~~~~~~~~~~~~~~~~~~~

Documentation source is also in Git. ReadTheDocs builds are automatic.

Monitoring and Logs
-------------------

Jekyll Logs
~~~~~~~~~~~

Jekyll outputs logs to console. Redirect to file::

    bundle exec jekyll serve > jekyll.log 2>&1

Health Checks
~~~~~~~~~~~~~

**Website availability**::

    curl -I https://studyflow-app.github.io

Security Maintenance
--------------------

Dependency Updates
~~~~~~~~~~~~~~~~~~

Check for security vulnerabilities::

    # Ruby
    bundle audit
    
    # Node.js (future)
    npm audit
    npm audit fix

Getting Help
------------

If you can't resolve an issue:

* Check the :doc:`faq`
* Search `GitHub Issues <https://github.com/luisjarquec/studyflow-app/issues>`_
* Ask on `Discord <https://discord.gg/v2ctzYdp>`_
* Open a new issue with detailed information

Reporting Bugs
--------------

When reporting bugs, include:

1. **Environment**: OS, Ruby/Node.js version, browser
2. **Steps to reproduce**
3. **Expected vs actual behavior**
4. **Error messages and logs**
5. **Screenshots** (if applicable)

See :doc:`contributing` for more details on bug reports.
