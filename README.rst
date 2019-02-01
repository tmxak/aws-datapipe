==============
 AWS-Datapipe
==============

A tool for creating AWS data pipeline. Currently only for **exporting data from any DynamoDB table to an existing S3 bucket** and store the Pipeline Definition as a backup.
New features are going to be added (check for updates).

Just because terraform can't do it yet..

---------------
 Prerequisites
---------------

The easiest way to install aws-cli is to use `pip <https://pypi.org/project/pip/>`_ in a ``virtualenv``::

    $ pip install awscli

or, if you are not installing in a ``virtualenv``, to install globally::

    $ sudo pip install awscli

or for your user::

    $ pip install --user awscli

If you have the aws-cli installed and want to upgrade to the latest version
you can run::

    $ pip install --upgrade awscli

---------------
 Installing
---------------

The easiest way to install aws-datapipe is to use `pip <https://pypi.org/project/pip/>`_ in a ``virtualenv``::

    $ pip install aws-datapipe

or, if you are not installing in a ``virtualenv``, to install globally::

    $ sudo pip install aws-datapipe

or for your user::

    $ pip install --user aws-datapipe

If you have the aws-datapipe installed and want to upgrade to the latest version
you can run::

    $ pip install --upgrade aws-datapipe


End with an example of getting some data out of the system or using it for a little demo

-------------------
 Running the tests
-------------------

Unfortunately there are no any tests yet..

---------------
Getting Started
---------------
Because aws-datapipe is based on aws-cli, before using aws-datapipe, 
you need to configure your AWS credentials using aws-cli.  
You can do this in several ways:

* Environment variables
* Shared credentials file
* Config file
* IAM Role

The quickest way to get started is to run the ``aws configure`` command::

    $ aws configure
    AWS Access Key ID: foo
    AWS Secret Access Key: bar
    Default region name [us-west-2]: us-west-2
    Default output format [None]: json

To use environment variables, do the following::

    $ export AWS_ACCESS_KEY_ID=<access_key>
    $ export AWS_SECRET_ACCESS_KEY=<secret_key>

To use the shared credentials file, create an INI formatted file like this::

    [default]
    aws_access_key_id=foo
    aws_secret_access_key=bar

    [testing]
    aws_access_key_id=foo
    aws_secret_access_key=bar

and place it in ``~/.aws/credentials`` (or in
``%UserProfile%\.aws/credentials`` on Windows). If you wish to place the
shared credentials file in a different location than the one specified above,
you need to tell aws-cli where to find it.  Do this by setting
the appropriate environment variable::

    $ export AWS_SHARED_CREDENTIALS_FILE=/path/to/shared_credentials_file

To use a config file, create a configuration file like this::

    [default]
    aws_access_key_id=<default access key>
    aws_secret_access_key=<default secret key>
    # Optional, to define default region for this profile.
    region=us-west-1

    [profile testing]
    aws_access_key_id=<testing access key>
    aws_secret_access_key=<testing secret key>
    region=us-west-2

and place it in ``~/.aws/config`` (or in ``%UserProfile%\.aws\config`` on Windows). If you wish to place the config file in a different location than the one
specified above, you need to tell aws-cli where to find it.  Do this by setting
the appropriate environment variable::

    $ export AWS_CONFIG_FILE=/path/to/config_file

As you can see, you can have multiple ``profiles`` defined in both the shared
credentials file and the  configuration file. You can then specify which
profile to use by using the ``--profile`` option. If no profile is specified
the ``default`` profile is used.

In the config file, except for the default profile, you
**must** prefix each config section of a profile group with ``profile``.
For example, if you have a profile named "testing" the section header would
be ``[profile testing]``.

The final option for credentials is highly recommended if you are
using aws-cli on an EC2 instance.  IAM Roles are
a great way to have credentials installed automatically on your
instance.  If you are using IAM Roles, aws-cli will find them and use
them automatically.

-----------
Versioning
-----------

I use `SemVer <http://semver.org/>`_ for versioning. For the versions available, see the `tags on this repository <https://github.com/tmxak/aws-datapipe/tags>`_. 

-------
Author
-------

* **Maxim Tacu** - Site Reliability Engineer - `OLX Group <https://www.olxgroup.com/>`_.

-------
License
-------

This project is licensed under the MIT License - see the `LICENSE <LICENSE>`_ file for details