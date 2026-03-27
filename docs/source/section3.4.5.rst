
.. _section3.4.5:

3.4.5 - Set Help File Information
=====================


.. _SH:

Action Option -**SH** (-**SetHelpFile**) (Alias: -**SetHelp**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates new or updates existing Help
  file records (Documents and Software) in GDEXDB for the specified dataset.
  Multiple records can be processed in a single run.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(SH|SetHelpFile) [`Mode Options <mode_>`_]
|         [-(`HF|HelpFile <section5.2_>`_) HelpFileNames]
|         [-(`WU|WebURL <section5.2_>`_) RemoteFileWebURL]
|         [-(`SR|Source <section5.2_>`_) ContributionSource]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`OB|OrderBy <section5.2_>`_) OrderByPattern]
|         [-(`HT|HelpFileType <section5.2_>`_) HelpFileTypes]
|         [-(`FS|FileStatus <section5.2_>`_) HelpFileStatus]
|         [-(`FF|FileFlag <section5.2_>`_) FilesOrPaths]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`DF|DataFormat <section5.2_>`_) DataFormats]
|         [-(`AF|ArchiveFormat <section5.2_>`_) FileArchiveFormats]
|         [-(`DO|DisplayOrder <section5.2_>`_) DisplayOrderIndices]
|         [-(`SZ|Size <section5.2_>`_) FileSizes]
|         [-(`MC|MD5Checksum <section5.2_>`_) MD5ChecksumValues]
|         [-(`ID|InitialDate <section5.2_>`_) HelpFileInitialDate]
|         [-(`FD|FileDate <section5.2_>`_) DateModified]
|         [-(`FT|FileTime <section5.2_>`_) TimeModified]
|         [-(`DE|Description <section5.2_>`_) SavedFileDescriptions]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
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
   * - -(`RO|ResetOrder <section4_>`_)
     - resets display order indices to match the order files are provided
   * - -(`SC|SetChecksum <section4_>`_)
     - computes MD5 checksums for Help files and saves them to GDEXDB

  Help file names must be provided via -`HF <section5.2_>`_ (-HelpFile) unless -`ON <section5.1_>`_ (-OrderNames)
  is used to reorder files. The number of values supplied to other `Info <section5>`_ options
  must match the number of file names, except for options that accept a single
  shared value, such as -`AF <section5.2_>`_, -`DF <section5.2_>`_, and -`HT <section5.2_>`_ (-HelpFileType).

  For remotely hosted Help files (e.g., on GitHub), provide the full URL via
  -`WU <section5.2_>`_ (-WebURL) to add a record without a local copy on the GDEX Server.




:ref:`Back to Top <index>`
