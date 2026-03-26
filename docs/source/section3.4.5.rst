
.. _section3.4.5:

3.4.5 - Set Help File Information
=====================


.. _SH:

Action Option -**SH** (-**SetHelpFile**) (Alias: -**SetHelp**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates and modifies information of Help
  files, Documents and Software, in RDADB for a given dataset. One or multiple
  files can be processed each time.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(SH|SetHelpFile) [`Mode Options <#mode>`_]
|   [-(`HF|HelpFile <section5.2.rst#HF>`_) HelpFileNames]
|   [-(`WU|WebURL <section5.2.rst#WU>`_) RemoteFileWebURL]
|   [-(`SR|Source <section5.2.rst#SR>`_) ContributionSource]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`HT|HelpFileType <section5.2.rst#HT>`_) HelpFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) HelpFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`DF|DataFormat <section5.2.rst#DF>`_) DataFormats]
|   [-(`AF|ArchiveFormat <section5.2.rst#AF>`_) FileArchiveFormats]
|   [-(`DO <section5.2.rst#DO>`_|DisplayOrder] DisplayOrderIndices]
|   [-(`SZ|Size <section5.2.rst#SZ>`_) FileSizes]
|   [-(`MC|MD5Checksum <section5.2.rst#MC>`_) MD5ChecksumValues]
|   [-(`ID|InitialDate <section5.2.rst#ID>`_) HelpFileInitialDate]
|   [-(`FD|FileDate <section5.2.rst#FD>`_) DateModified]
|   [-(`FT|FileTime <section5.2.rst#FT>`_) TimeModified]
|   [-(`DE <section5.2.rst#DE>`_|Description] SavedFileDescriptions]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for setting Web file action:

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
   * - -(`RO|ResetOrder <section4.rst#RO>`_)
     - resets the ordering indices of the list of file names according to the order they are provided
   * - -(`SC|SetChecksum <section4.rst#SC>`_)
     - evaluates the md5 checksum values for Helpfiles and saves them into RDADB

  Help file names must be provided per option -`HF <section5.2.rst#HF>`_ (-HelpFile) for this action to
  work, unless `Info Option <section5.rst>`_ -`ON <section5.1.rst#ON>`_ (-OrderNames) is provided to reorder Help files
  of specified dataset and groups. The number of values passed in following
  `Info <section5.rst>`_ options should match the number of file names given per option -`HF <section5.2.rst#HF>`_,
  except for options related to dataset information and the `Info <section5.rst>`_ options that
  are allowed to pass in single values, such as -`AF <section5.2.rst#AF>`_ (-ArchiveFormat), -`DF <section5.2.rst#DF>`_
  (-DataFormat), and -`HT <section5.2.rst#HT>`_ (-HelpFileType).

  For a Help file located remotely, such as on github, a Help file record can be
  added into RDADB via action -`SH <#SH>`_ and a full URL link is provided via option -`WU <section5.2.rst#WU>`_.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
