.. image:: https://img.shields.io/coveralls/github/timcera/tsgettoolbox_ndbc
    :alt: Test Coverage
    :target: https://coveralls.io/r/timcera/tsgettoolbox_ndbc?branch=master
    :height: 20

.. image:: https://img.shields.io/pypi/v/tsgettoolbox_ndbc
    :alt: Latest release
    :target: https://pypi.python.org/pypi/tsgettoolbox_ndbc/
    :height: 20

.. image:: https://img.shields.io/pypi/l/tsgettoolbox_ndbc
    :alt: BSD-3 clause license
    :target: https://pypi.python.org/pypi/tsgettoolbox_ndbc/
    :height: 20

.. image:: https://img.shields.io/pypi/pyversions/tsgettoolbox_ndbc
    :alt: PyPI - Python Version
    :target: https://pypi.org/project/tsgettoolbox_ndbc/
    :height: 20

tsgettoolbox_ndbc - Quick Guide
===============================
The 'tsgettoolbox_ndbc' is a plugin-in for 'tsgettoolbox' that supplies
a command line interface and Python library to get time-series data from the
National Data Buoy Center (NDBC).  The tsgettoolbox_ndbc will work with
Python 3.10+.

Documentation
-------------
Reference documentation is at `tsgettoolbox_documentation`_.

Installation
------------
At the command line::

    $ pip install tsgettoolbox_ndbc

    OR

    $ conda install -c conda-forge tsgettoolbox_ndbc

Usage Summary - Command Line
----------------------------
Just run 'tsgettoolbox --help' to get a list of subcommands.  To get detailed
help for a particular sub-command, for instance 'ndbc', type 'tsgettoolbox
ndbc --help'.

+-------------+---------+--------+---------+----------+-----------------------+
| Sub-command | Spatial | Time   | Type    | Time     | Description           |
|             | Extent  | Extent |         | Interval |                       |
+=============+=========+========+=========+==========+=======================+
| ndbc        | US      | varies | station | 6T,10T,  | National Data Buoy    |
|             |         |        |         | 15T,H,D  | Center                |
+-------------+---------+--------+---------+----------+-----------------------+

+-------------------+-------------+
| Time Interval     | Description |
| Code              |             |
+===================+=============+
| T                 | Minute      |
+-------------------+-------------+
| H                 | Hourly      |
+-------------------+-------------+
| D                 | Daily       |
+-------------------+-------------+

Usage Summary - Python Library
------------------------------
To use the tsgettoolbox in a project::

    from tsgettoolbox import tsgettoolbox
    df = tsgettoolbox.ndbc("pfdc1", "stdmet", startUTC="2020-01-01", endUTC="2020-02-01")
    print(df.head())

Refer to the API Documentation at `tsgettoolbox NDBC API`_.

Usage Summary - Command Line
----------------------------

    tsgettoolbox ndbc pfdc1 stdmet 2020-01-01 --endUTC 2020-02-01 > output.csv

Refer to the command line documentation at `tsgettoolbox NDBC CLI`_.

Development
~~~~~~~~~~~
Development is managed on bitbucket or github.
https://bitbucket.org/timcera/tsgettoolbox_ndbc/overview.
https://github.com/timcera/tsgettoolbox_ndbc

.. _tsgettoolbox_documentation: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/index.html
.. _tsgettoolbox NDBC API: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/_function_autosummary/tsgettoolbox.ndbc.html
.. _tsgettoolbox NDBC CLI: https://timcera.bitbucket.io/linked_pkg_dirs/tsgettoolbox/docs/command_line.html#ndbc
