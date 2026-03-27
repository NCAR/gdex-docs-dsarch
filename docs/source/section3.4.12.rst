
.. _section3.4.12:

3.4.12 - Backup Quasar Files
=====================


.. _AQ:

Action Option -**AQ** (-**ArchiveQuasarFile**) (Aliases: -**ArchiveQuasar**, -**ArchiveBackupFile**, -**ArchiveBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 (Alias: -ArchiveQuasar|-ArchiveBackupFile|-ArchiveBackup),
  backs the archived saved and/or Web files up onto Globus Quasar Servers and saves
  their information into RDADB. All the provided saved and/or web files are backed
  up into a single Quasar backup file at a time. Another utility program, dsquasar,
  is normally used to check and collect the newly archived saved and web files.
  The dsquasar builds input files between 1 and 3 GB, and then call the dsarch to
  build a tarfile and back the tar file onto Quasar server. Reference to dsquasar
  help document for detail information.

| **dsarch** [-(`DS|dataset <section5.1.rst#DS>`_)] dsnnn.n -(AQ|ArchiveQuasarFile) [`Mode Options <#mode>`_]
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
   * - -(`OE|OverrideExist <section4.rst#OE>`_)
     - overrides existing web files
   * - -(`TO|TarOnly <section4.rst#TO>`_)
     - to tar the given Saved and/or Web files only, without physically backing up the Quasar file onto the Globus Quasar Server.
   * - -(`XC|CrossCopy <section4.rst#XC>`_)
     - copies files from existing Quasar Backup and Disaster Recovery files to missing Backup/Drdata files; information of the quasar backup files saved in RDADB is used for missing data copies

  One or multiple Saved/Web file names can be provided per option -`SF <section5.2.rst#SF>`_/-WF,
  respectively, and for this action to work.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
