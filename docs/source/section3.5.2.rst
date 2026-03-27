
.. _section3.5.2:

3.5.2 - Set All Information
=====================


.. _SA:

Action Option -**SA** (-**SetALL**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates and updates all dataset, group, and
Saved/Web/Help/Quasar file records for a dataset in one step. Equivalent to
running -:ref:`SD <SD>`, -:ref:`SG <SG>`, -:ref:`SS <SS>`, -:ref:`SW <SW>`, -:ref:`SH <SH>`, and -:ref:`SQ <SQ>` together.

dsarch  :ref:`-(SA|SetAll) <SA>` [:ref:`Mode Options <section4>`]
[:ref:`-(LN|LoginName) <LN>` LoginAccountName]
:ref:`-(IF|InputFile) <IF>` Input Files
[:ref:`-(DB|Debug) <DB>` DebugModeInfo]

All :ref:`Mode options <section4>` applicable to the individual Set actions may be used with
-:ref:`SA <SA>`. At least one input file is required, since section headers can only be
specified in an input file. A typical workflow: run -:ref:`GA <GA>` (-GetAll) to export
all records, edit the output file as needed, then feed it back with -:ref:`SA <SA>`.




:ref:`Back to Top <index>`
