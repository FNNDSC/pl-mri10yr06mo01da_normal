pl-mri10yr06mo01da_normal
================================

.. image:: https://badge.fury.io/py/mri10yr06mo01da_normal.svg
    :target: https://badge.fury.io/py/mri10yr06mo01da_normal

.. image:: https://travis-ci.org/FNNDSC/mri10yr06mo01da_normal.svg?branch=master
    :target: https://travis-ci.org/FNNDSC/mri10yr06mo01da_normal

.. image:: https://img.shields.io/badge/python-3.5%2B-blue.svg
    :target: https://badge.fury.io/py/pl-mri10yr06mo01da_normal

.. contents:: Table of Contents


Abstract
--------

This application simply copies from embedded data a reference normal anonymized MRI of a subject aged 10 years, 06 months, 01 days.


Synopsis
--------

.. code:: bash

    python mri10yr06mo01da_normal.py                                           \
        [-v <level>] [--verbosity <level>]                          \
        [--version]                                                 \
        [--man]                                                     \
        [--meta]                                                    \
        <inputDir>
        <outputDir> 


Run
----

This ``plugin`` can be run in two modes: natively as a python package or as a containerized docker image.

Using PyPI
~~~~~~~~~~

To run from PyPI, simply do a 

.. code:: bash

    pip install mri10yr06mo01da_normal

and run with

.. code:: bash

    mri10yr06mo01da_normal.py --man /tmp /tmp

to get inline help. The app should also understand being called with only two positional arguments

.. code:: bash

    mri10yr06mo01da_normal.py /some/input/directory /destination/directory


Using ``docker run``
~~~~~~~~~~~~~~~~~~~~

To run using ``docker``, be sure to assign an "input" directory to ``/incoming`` and an output directory to ``/outgoing``. *Make sure that the* ``$(pwd)/out`` *directory is world writable!*

Now, prefix all calls with 

.. code:: bash

    docker run --rm -v $(pwd)/out:/outgoing                             \
            fnndsc/pl-mri10yr06mo01da_normal mri10yr06mo01da_normal.py                        \

Thus, getting inline help is:

.. code:: bash

    mkdir in out && chmod 777 out
    docker run --rm -v $(pwd)/in:/incoming -v $(pwd)/out:/outgoing      \
            fnndsc/pl-mri10yr06mo01da_normal mri10yr06mo01da_normal.py                        \
            --man                                                       \
            /incoming /outgoing

Examples
--------





