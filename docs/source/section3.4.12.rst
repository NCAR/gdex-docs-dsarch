
.. _section3.4.12:

3.4.12 - Backup Quasar Files
=====================


.. _AQ:

Action Option -**AQ** (-**ArchiveQuasarFile**) (Aliases: -**ArchiveQuasar**, -**ArchiveBackupFile**, -**ArchiveBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 (Alias: -ArchiveQuasar|-ArchiveBackupFile|-ArchiveBackup),
  packages archived Saved and/or Web files into a single tar file and uploads it
  to the Globus Quasar Server for long-term backup, recording the result in
  GDEXDB. In practice, the companion utility 'dsquasar' handles identifying
  files to back up, building optimally sized input lists (1-3 GB each), and
  calling this action. See 'dsquasar' help for details.

| **dsarch** [-(`DS|dataset <section5.1_>`_)] dNNNNNN -(AQ|ArchiveQuasarFile) [`Mode Options <mode_>`_]
|         [-(`SF|SavedFile <section5.2_>`_) SavedFileNames]
|         [-(`ST|SavedFileType <section5.2_>`_) SavedFileTypes]
|         [-(`WF|WebFile <section5.2_>`_) webFileNames]
|         [-(`WT|WebFileType <section5.2_>`_) WebFileTypes]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`QS|QsubOptions <section5.1_>`_)  PBSBatchOptions]
|         [-(`BP|BatchProcess <section5.2_>`_) [BatchControlInfo]]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4_>`_)
     - runs in background; suppresses screen output and errors
   * - -(`EM|EMailNotice <section4_>`_)
     - sends an email summary (including any errors) when the action completes or aborts
   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NE|NoEmail <section4_>`_)
     - suppresses email notification on failure
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`OE|OverrideExist <section4_>`_)
     - overwrites existing Quasar files
   * - -(`TO|TarOnly <section4_>`_)
     - creates the tar file only, without uploading it to the Globus Quasar Server
   * - -(`XC|CrossCopy <section4_>`_)
     - copies files from existing Quasar Backup and Disaster Recovery files to fill missing Backup/Drdata copies, using GDEXDB records for guidance

  At least one Saved and/or Web file name must be provided via -`SF <section5.2_>`_ and/or -`WF <section5.2_>`_.




:ref:`Back to Top <index>`
