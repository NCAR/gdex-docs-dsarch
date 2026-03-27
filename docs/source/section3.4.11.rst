
.. _section3.4.11:

3.4.11 - Archive Help Files
=====================


.. _AH:

Action Option -**AH** (-**ArchiveHelpFile**) (Aliases: -**ArchiveHelp**, -**ArchHelp**, -**ArchHelpFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 (Alias: -ArchiveHelp|-ArchHelp|-ArchHelpFile),
  copies local files to the GDEX Server as Help files (Documents and Software)
  and registers them in GDEXDB. One or more files may be archived per execution.

| **dsarch** [-(`DS|dataset <section5.1_>`_)] dNNNNNN -(AH|ArchiveHelpFile) [`Mode Options <mode_>`_]
|         -(`LF|LocalFile <section5.2_>`_) LocalFileNames
|         [-(`HF|HelpFile <section5.2_>`_) HelpFileNames]
|         [-(`HT|HelpFileType <section5.2_>`_) HelpFileTypes]
|         [-(`FS|FileStatus <section5.2_>`_) HelpFileStatus]
|         [-(`FF|FileFlag <section5.2_>`_) FilesOrPaths]
|         [-(`DF|DataFormat <section5.2_>`_) FileContentFormat]
|         [-(`AF|ArchiveFormat <section5.2_>`_) FileArchiveFormat]
|         [-(`DO|DisplayOrder <section5.2_>`_) DisplayOrderIndices]
|         [-(`SZ|Size <section5.2_>`_) FileSizes]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`MC|MD5Checksum <section5.2_>`_) MD5ChecksumValues]
|         [-(`DE|Description <section5.2_>`_) SavedFileDescriptions]
|         [-(`VS|ValidSize <section5.1_>`_) MinSizeForValidFile]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`QS|QsubOptions <section5.1_>`_)  PBSBatchOptions]
|         [-(`BP|BatchProcess <section5.2_>`_) [BatchControlInfo]]
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteLocalDirLevel]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4_>`_)
     - runs in background; suppresses screen output and errors
   * - -(`CL|CleanLocal <section4_>`_)
     - removes local files after all are successfully archived
   * - -(`EM|EMailNotice <section4_>`_)
     - sends an email summary (including any errors) when the action completes or aborts
   * - -(`GZ|GMTZone <section4_>`_)
     - uses GMT rather than local time for archiving timestamps
   * - -(`KP|KeepLocalPath <section4_>`_)
     - uses local file paths as relative paths on the GDEX Server
   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NE|NoEmail <section4_>`_)
     - suppresses email notification on failure
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`OE|OverrideExist <section4_>`_)
     - overwrites existing Help files
   * - -(`RO|ResetOrder <section4_>`_)
     - resets display order indices to match the order files are given per -`HF <section5.2_>`_. Alternatively, use -`ON <section5.1_>`_ (-OrderNames) to reorder all files in the dataset and affected groups
   * - -(`SC|SetChecksum <section4_>`_)
     - computes MD5 checksums for Help files and saves them to GDEXDB

  Local file names are provided via -`LF <section5.2_>`_ (-LocalFile). On the command line,
  '*' and '?' wildcards are supported. Files not in the current directory must
  include relative or absolute paths. If a directory is given via -`LD <section5.1_>`_
  (-LocalDirectory), files are gathered recursively.

  Local file names are used as Help file names by default unless -`HF <section5.2_>`_ (-HelpFile)
  is given explicitly. When -`KP <section4_>`_ (-KeepLocalPath) is specified, local file paths
  are used as-is on the GDEX Server.

  The number of values supplied to `Info <section5>`_ options must match the number of local
  file names, except for options that accept a single shared value: -`DF <section5.2_>`_, -`AF <section5.2_>`_,
  and -`HT <section5.2_>`_ (-HelpFileType).

  The storage location is set via -`LC <section5.2_>`_ (-Location). Defaults to 'B' (both Web
  Disk and Object Store).




:ref:`Back to Top <index>`
