
.. _section3.5.2:

3.5.2 - Set All Information
=====================


.. _SA:

Action Option -**SA** (-**SetALL**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates and updates all dataset, group, and
  Saved/Web/Help/Quasar file records for a dataset in one step. Equivalent to
  running -`SD <section3.1.1_>`_, -`SG <section3.3.1_>`_, -`SS <section3.4.1_>`_, -`SW <section3.4.3_>`_, -`SH <section3.4.5_>`_, and -`SQ <section3.4.7_>`_ together.

  dsarch  -(`SA|SetAll <SA_>`_) [`Mode Options <section4>`_]
         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
          -(`IF|InputFile <section5.2_>`_) Input Files
         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

  All `Mode <section4>`_ options applicable to the individual Set actions may be used with
  -`SA`_. At least one input file is required, since section headers can only be
  specified in an input file. A typical workflow: run -`GA <section3.5.1_>`_ (-GetAll) to export
  all records, edit the output file as needed, then feed it back with -`SA`_.




:ref:`Back to Top <index>`
