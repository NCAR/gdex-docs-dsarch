
.. _section3:

3 - ACTION OPTIONS
=====================

Action options tell **dsarch** what to do. They take no values. Some actions
perform a single task; others bundle multiple tasks together and may trigger
additional steps when certain `Mode <section4>`_ options are present. Only one Action option
may be specified per execution.

Write actions require the -`UD <section5.1_>`_ (-UseDSARCH) flag to be set to 'Y', 'I', 'P',
or 'W' for the target dataset before they can modify GDEXDB. Read actions
have no such requirement.

Actions are grouped into seven categories based on the information they handle:

.. list-table::
   :widths: auto

   * - `Dataset Actions <section3.1>`_
     - create, modify and retrieve dataset information in GDEXDB
   * - `DOI/Version Actions <section3.2>`_
     - add, modify, view and terminate DOI/Version control for a given dataset
   * - `Group Actions <section3.3>`_
     - create, delete, modify and retrieve group information in GDEXDB, of a given dataset
   * - `File Actions <section3.4>`_
     - archive local data files as Saved/Web/Help files; move and delete archived files on GDEX Server; create, delete, modify and retrieve information of archived files in GDEXDB, of a given dataset, and groups if specified
   * - `All Info Actions <section3.5>`_
     - create, modify and retrieve all information, of dataset, groups and files of a given dataset in GDEXDB
   * - `Webpage Actions <section3.6>`_
     - regenerate dataset main and filelist webpages

.. toctree::
   :maxdepth: 2
   :caption: Table of Contents

   section3.1
   section3.1.1
   section3.1.2
   section3.2
   section3.2.1
   section3.2.2
   section3.2.3
   section3.3
   section3.3.1
   section3.3.2
   section3.3.3
   section3.3.4
   section3.4
   section3.4.1
   section3.4.2
   section3.4.3
   section3.4.4
   section3.4.5
   section3.4.6
   section3.4.7
   section3.4.8
   section3.4.9
   section3.4.10
   section3.4.11
   section3.4.12
   section3.4.13
   section3.4.14
   section3.4.15
   section3.5
   section3.5.1
   section3.5.2
   section3.6
   section3.6.1
   section3.6.2

**Appendix A: List of Examples**

- `A.1. Action Option -SD (-SetDataset) <3.1.1_e1>`_
- `A.2. Action Option -GD (-GetDataset) <3.1.2_e2>`_
- `A.3. Action Option -SV (-SetVersion) <3.2.1_e3>`_
- `A.4. Action Option -GV (-GetVersion) <3.2.2_e4>`_
- `A.5. Action Option -TV (-TerminateVersion) <3.2.3_e5>`_
- `A.6. Action Option -SG (-SetGroup) <3.3.1_e6>`_
- `A.7. Action Option -GG (-GetGroup) <3.3.2_e7>`_
- `A.8. Action Option -DG (-DeleteGroup) <3.3.3_e8>`_
- `A.9. Action Option -CG (-ChangeGroup) <3.3.4_e9>`_
- `A.10. Action Option -GW (-GetWebFile) <3.4.4_e10>`_




:ref:`Back to Top <index>`
