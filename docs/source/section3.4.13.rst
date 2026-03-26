
.. _section3.4.13:

3.4.13 - Restore Quasar Files
=====================


.. _RQ:

Action Option -**RQ** (-**RestoreQuasarFile**) (Aliases: -**RestoreQuasar**, -**RestoreBackupFile**, -**RestoreBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 (Alias: -RestoreQuasar|RestoreBackupfile|-RestoreBackup),
  identifies Quasar files from given saved and/or Web files, retrieves the tarfiles from
  Globus Quasar Server, and restores the Saved and/or Web files if any missed.

| **dsarch** [-(`DS|dataset <section5.1.rst#DS>`_)] dsnnn.n -(RQ|RestoreQuasarFile) [`Mode Options <#mode>`_]
|   [-(`QF|QuasarFile <section5.2.rst#QF>`_) QuasarFileNames]
|   [-(`SF|SavedFile <section5.2.rst#SF>`_) SavedFileNames]
|   [-(`ST|SavedFileType <section5.2.rst#ST>`_) SavedFileTypes]
|   [-(`WF|WebFile <section5.2.rst#WF>`_) webFileNames]
|   [-(`WT|WebFileType <section5.2.rst#WT>`_) WebFileTypes]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`QS|QsubOptions <section5.1.rst#QS>`_)  PBSBatchOptions]
|   [-(`BP|BatchProcess <section5.2.rst#BP>`_) [BatchControlInfo]]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for archive web file action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4.rst#BG>`_)
     - background process to turn off screen display for both standard outputs and errors
   * - -(`EM|EMailNotice <section4.rst#EM>`_)
     - sends email for summary and errors for this action
   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NE|NoEmail <section4.rst#NE>`_)
     - does not send email to the specialist for failed action
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)

  One or multiple Quasar/Saved/Web file names can be provided per option -`QF <section5.2.rst#QF>`_-SF/-`WF <section5.2.rst#WF>`_,
  for this action to work. If Only Quasar file names are provided, the quasar tarfiles
  are retrieved from quasar Server, but no Saved or Web files are retored.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
