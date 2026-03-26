
.. _section3:

3 - ACTION OPTIONS
=====================

Action options are used to specify what task **dsarch** executes. No values
are allowed to follow Action options. Multiple tasks may be processed with a
single execution of **dsarch** depending on what Action option is chosen. Some of
the comprehensive actions include automatically other simpler actions as
default; and others include additional actions when certain `Mode <section4.rst>`_ options are
present. Multiple Action options provided simultaneously are blocked.

Some actions are setting information into and some getting information from
RDADB for a given dataset. A using DSARCH flag must be set to 'Y', 'I', 'P', or
'W' per `Info <section5.rst>`_ option -`UD <section5.1.rst#UD>`_ (-UseDSARCH) before setting actions can be executed
for a dataset.

Based on the information being manipulated, the actions are divided into seven
categories:

.. list-table::
   :widths: auto

   * - `Dataset Actions <section3.1.rst>`_
     - create, modify and retrieve dataset information in RDADB
   * - `DOI/Version Actions <section3.2.rst>`_
     - add, modify, view and terminate DOI/Version control for a given dataset
   * - `Group Actions <section3.3.rst>`_
     - create, delete, modify and retrieve group information in RDADB, of a given dataset
   * - `File Actions <section3.4.rst>`_
     - archive local data files as Saved/Web/Help files; move and delete archived files on RDA Server; create, delete, modify and retrieve information of archived files in RDADB, of a given dataset, and groups if specified
   * - `All Info Actions <section3.5.rst>`_
     - create, modify and retrieve all information, of dataset, groups and files of a given dataset in RDADB
   * - `Webpage Actions <section3.6.rst>`_
     - regenerate dataset main and filelist webpages



.. raw:: html

   <br>

:ref:`Back to Top <index>`
