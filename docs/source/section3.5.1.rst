
.. _section3.5.1:

3.5.1 - Get All Information
=====================


.. _GA:

Action Option -**GA** (-**GetALL**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves dataset, group and Saved/Web/Help/Quasar file
  information for a given dataset. This is a comprehensive action, combining all Get
  Actions, -`GD <section3.1.2.rst>`_ (-GetDataset), -`GG <section3.3.2.rst>`_ (-GetGroup), -`GS <section3.4.2.rst>`_ (-GetSavedFile), -`GW <section3.4.4.rst>`_ (-GetWebFile),
  -`GH <section3.4.6.rst>`_ (-GetHelpFile), and -`GQ <section3.4.8.rst>`_ (-GetQuasarFile.

| **dsarch** [-(`DS|dataset <section5.1.rst#DS>`_)] dsnnn.n -(GA|GetAll)
|   [-(`OF <section5.1.rst#OF>`_|OutputFile|>) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

  No `Mode <section4.rst>`_ option is applied to this action. Information of all available fields
  is retrieved for dataset, groups and files.

  Section headers are generated as [DATASET] for dataset, [DSGROUP] for
  groups, [SAVEDFILE] for Saved file information, [WEBFILE] for Web file information,
  [HELPFILE] for Help file information, and [QUASARFILE] for Quasar file information.

  `Info <section5.rst>`_ option -`OF <section5.1.rst#OF>`_ (-OutputFile|>) is normally used to specify a file name to
  save the retrieved information for later usage. Result of this action is
  displayed on screen if no output file is provided. The output file can be
  edited and treated as a input file to save the changes back to RDADB per
  action -`SA <section3.5.2.rst>`_ (-SetAll).



.. raw:: html

   <br>

:ref:`Back to Top <index>`
