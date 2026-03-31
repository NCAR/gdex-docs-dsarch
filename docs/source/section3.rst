
.. _section3:

3 - ACTION OPTIONS
=================================

Action options tell **dsarch** what to do. They take no values. Some actions
perform a single task; others bundle multiple tasks together and may trigger
additional steps when certain :ref:`Mode options <section4>` are present. Only one Action option
may be specified per execution.

Write actions require the :ref:`-UD <UD>` (-UseDSARCH) flag to be set to 'Y', 'I', 'P',
or 'W' for the target dataset before they can modify GDEXDB. Read actions
have no such requirement.

Actions are grouped into seven categories based on the information they handle:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`Dataset Actions <section3.1>`
     - create, modify and retrieve dataset information in GDEXDB
   * - :ref:`DOI/Version Actions <section3.2>`
     - add, modify, view and terminate DOI/Version control for a given dataset
   * - :ref:`Group Actions <section3.3>`
     - create, delete, modify and retrieve group information in GDEXDB, of a given dataset
   * - :ref:`File Actions <section3.4>`
     - archive local data files as Saved/Web/Help files; move and delete archived files on GDEX Server; create, delete, modify and retrieve information of archived files in GDEXDB, of a given dataset, and groups if specified
   * - :ref:`All Info Actions <section3.5>`
     - create, modify and retrieve all information, of dataset, groups and files of a given dataset in GDEXDB
   * - :ref:`Webpage Actions <section3.6>`
     - regenerate dataset main and filelist webpages

.. toctree::
   :maxdepth: 2
   :caption: Table of Contents

   section3.1
   section3.2
   section3.3
   section3.4
   section3.5
   section3.6

**Appendix A: List of Examples**

- :ref:`A.1. Action Option -SD (-SetDataset) <3.1.1_e1>`
- :ref:`A.2. Action Option -GD (-GetDataset) <3.1.2_e2>`
- :ref:`A.3. Action Option -SV (-SetVersion) <3.2.1_e3>`
- :ref:`A.4. Action Option -GV (-GetVersion) <3.2.2_e4>`
- :ref:`A.5. Action Option -TV (-TerminateVersion) <3.2.3_e5>`
- :ref:`A.6. Action Option -SG (-SetGroup) <3.3.1_e6>`
- :ref:`A.7. Action Option -GG (-GetGroup) <3.3.2_e7>`
- :ref:`A.8. Action Option -DG (-DeleteGroup) <3.3.3_e8>`
- :ref:`A.9. Action Option -CG (-ChangeGroup) <3.3.4_e9>`
- :ref:`A.10. Action Option -GW (-GetWebFile) <3.4.4_e10>`



| :ref:`Back to Top <section3>`
| :ref:`Back to Table of Contents <index>`
