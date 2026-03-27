
.. _section3.4.13:

3.4.13 - Restore Quasar Files
=====================


.. _RQ:

Action Option -**RQ** (-**RestoreQuasarFile**) (Aliases: -**RestoreQuasar**, -**RestoreBackupFile**, -**RestoreBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 (Alias: -RestoreQuasar|-RestoreBackupFile|-RestoreBackup),
  finds the Quasar tar files that contain the specified Saved and/or Web files,
  downloads them from the Globus Quasar Server, and restores any files that
  are missing from the GDEX Server.

| **dsarch** [-(`DS|dataset <section5.1_>`_)] dNNNNNN -(RQ|RestoreQuasarFile) [`Mode Options <mode_>`_]
|         [-(`QF|QuasarFile <section5.2_>`_) QuasarFileNames]
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

  At least one Quasar, Saved, and/or Web file name must be provided via -`QF <section5.2_>`_,
  -`SF <section5.2_>`_, and/or -`WF <section5.2_>`_. If only Quasar file names are given, the tar files are
  retrieved from the server but no Saved or Web files are restored.




:ref:`Back to Top <index>`
