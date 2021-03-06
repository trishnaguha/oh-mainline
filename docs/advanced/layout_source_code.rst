=================================
Layout of OpenHatch's source code
=================================

This section should help developers get a better understanding of OpenHatch's
``oh-mainline`` repository.

This section is a basic overview. Additional details can be found in the
``LAYOUT`` file in the root directory of ``oh-mainline``.


Directory structure
===================


docs/
    This directory contains documentation files for OpenHatch and is
    rendered at RTD ReadtheDocs <http://openhatch.readthedocs.org>.

downloads/
    This directory may be used by deployment for temporary storage.

    [FUTURE: It may be possible to remove this directory in a later
    release.]

htmlcov/
    This directory stores reports created by the coverage testing tool.

mysite/
    This directory contains the OpenHatch website and all the "Django
    apps" that are part of it. Each subdirectory is an app.

    Each of the apps has some tests, views, and frequently models and forms.
    Their file paths are:

        /tests.py

        /views.py

        /forms.py

        /models.py

    You can read more about tests, views, forms, and models in the
    official Django tutorial:

        https://docs.djangoproject.com/en/1.5/intro/tutorial01/

    customs/
        This directory contains "import/export" code like the support for
        loading and saving snapshots of the OpenHatch database, downloading
        data from bug trackers, and scanning other websites for information
        about OpenHatch members.

    profile/
        This app contains code on information about OpenHatch users.

    account/
        This app (mostly) contains code to let a user edit their information.

    missions/
        This is the Django app where the training missions live.

    search/
        This Django app contains the views and models necessary to display
        the volunteer opportunity finder, also known as bug search.

    The apps also use other Django features, or Django add-ons. Here is a
    list by filename and a URL reference to further info:

    /templatetags.py
        https://docs.djangoproject.com/en/1.5/howto/custom-template-tags/

    /migrations/
        http://south.aeracode.org/

    /api.py
        http://django-tastypie.readthedocs.org/

    /fixtures.json
        https://docs.djangoproject.com/en/1.5/howto/initial-data/

    /management/commands
       https://docs.djangoproject.com/en/1.5/howto/custom-management-commands/

    /view_helpers.py
       http://lists.openhatch.org/pipermail/devel/2013-March/003151.html

    /templates/
       https://docs.djangoproject.com/en/1.5/topics/templates/

tools/
    This directory contains helper tools that make things easier for a
    contributor (for example, a script for rendering docs).

vendor/
    This directory contains code from other projects that we rely on.
    (For more information, look at
    http://kitsune.readthedocs.org/en/latest/vendor.html .)


Informational Files
===================
These informational files are found in the root directory of ``oh-mainline``.

README.rst
    Read the README! Read it first.

    It points to our main documentation; this LAYOUT file is just a quick
    thumbnail view of what different files in here are.

    (Aside: The ".rst" extension indicates reStructuredText format is used.)

LICENSE
    This file explains what permissions you have, if you want to re-use
    source code you find in this repository.

CREDITS
    This file gives credit for files used by OpenHatch.

LAYOUT
    This file (the one that you are viewing now) gives an overview of the
    project high-level directory and file structure.


dotfiles
========
In general, dotfiles provide configuration details.

    .coveragerc
        coverage testing configuration

    .gitattributes
        git

    .gitignore
        Files ignored by git

    .travis.yml
        Travis continuous integration configuration


Other files and executable files
================================
manage.py
    This is the well-known and widely-loved Django management script.

Procfile
    A file used when deploying the site.

requirements.txt
    This file indicates packages (i.e. ones that are not pure Python code
    and contain compiled code) that are installed in a different manner than
    packages found in the vendor directory.

run_importer.sh
    This shell script is used for deployment and running of scraping of
    projects for suitable bugs for contributors. [FUTURE: This file may
    be relocated to a different place.]

setup.py
    This file lists the dependencies of the OpenHatch codebase.