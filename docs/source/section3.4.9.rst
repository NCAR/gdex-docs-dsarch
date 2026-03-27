
.. _section3.4.9:

3.4.9 - Archive Saved Files
=====================


.. _AS:

Action Option -**AS** (-**ArchiveSavedFile**) (Aliases: -**ArchiveSaved**, -**ArchSaved**, -**ArchSavedFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 (Alias: -ArchiveSaved|-ArchSaved|-ArchSavedFile),
  copies local files to the GDEX Server as Saved files and registers them in
  GDEXDB. One or more files may be archived per execution.

| **dsarch** [-(`DS|dataset <section5.1_>`_)] dNNNNNN -(AS|ArchiveSavedFile) [`Mode Options <mode_>`_]
|         [-(`LF|LocalFile <section5.2_>`_) LocalFileNames]
|         [-(`LD|LocalDirectory <section5.1_>`_) LocalDirectoryName]
|         [-(`LL|LocalFileList <section5.1_>`_) LocalFileListName]
|         [-(`SF|SavedFile <section5.2_>`_) SavedFileNames]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|         [-(`GN|GroupName <section5.2_>`_) GroupNames]
|         [-(`TG|TopGroupIndex <section5.2_>`_) TopGroupIndices]
|         [-(`PO|PatternOffset <section5.1_>`_) PatternStringOffset]
|         [-(`ST|SavedFileType <section5.2_>`_) SavedFileTypes]
|         [-(`FS|FileStatus <section5.2_>`_) SavedFileStatus]
|         [-(`FF|FileFlag <section5.2_>`_) FilesOrPaths]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`DF|DataFormat <section5.2_>`_) DataFormat]
|         [-(`AF|ArchiveFormat <section5.2_>`_) FileArchiveFormat]
|         [-(`DO|DisplayOrder <section5.2_>`_) DisplayOrderIndices]
|         [-(`SZ|Size <section5.2_>`_) FileSizes]
|         [-(`MC|MD5Checksum <section5.2_>`_) MD5ChecksumValues]
|         [-(`DE|Description <section5.2_>`_) SavedFileDescriptions]
|         [-(`VS|ValidSize <section5.1_>`_) MinSizeForValidFile]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`AL|AsyncLimit <section5.1_>`_) AsyncProcessLimit]
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
     - overwrites existing Saved files
   * - -(`RO|ResetOrder <section4_>`_)
     - resets display order indices to match the order files are given per -`SF <section5.2_>`_. Alternatively, use -`ON <section5.1_>`_ (-OrderNames) to reorder all files in the dataset and affected groups
   * - -(`SC|SetChecksum <section4_>`_)
     - computes MD5 checksums for files on the GDEX Server and saves them to GDEXDB
   * - -(`UZ|UnzipData <section4_>`_)
     - decompresses files using 'gunzip', 'uncompress', 'unzip', or 'bunzip' according to the extension: '.gz', '.Z', '.zip', or '.bz2', respectively
   * - -(`XC|CrossCopy <section4_>`_)
     - copies files from existing Saved/Object storage to fill missing Object/Saved copies, using GDEXDB records for guidance
   * - -(`XM|CrossMove <section4_>`_)
     - moves files from existing Saved/Object storage to fill missing Object/Saved copies (originals are removed)
   * - -(`ZD|ZipData <section4_>`_)
     - compresses files using 'gzip', 'compress', 'zip', or 'bzip' according to the archive format ('GZ', 'Z', 'ZIP', or 'BZ2') given via -`AF <section5.2_>`_ (-ArchiveFormat)

  Local file names are provided via -`LF <section5.2_>`_ (-LocalFile). On the command line,
  '*' and '?' wildcards are supported. Files not in the current directory must
  include relative or absolute paths. If a directory is given via -`LD <section5.1_>`_
  (-LocalDirectory), files are gathered recursively from that tree.

  Local file names are used as Saved file names by default unless -`SF <section5.2_>`_
  (-SavedFile) is given explicitly. Files are archived under the dataset home
  directory; use -`SP <section5.2_>`_ (-SavedPath) or the path stored in GDEXDB to override.
  When -`KP <section4_>`_ (-KeepLocalPath) is specified, local file paths are used as-is on
  the GDEX Server and -`SP <section5.2_>`_ is not permitted.

  Assign files to a group via -`GI <section5.2_>`_ (-GroupIndex) or -`GN <section5.2_>`_ (-GroupName). If no
  group is specified, pattern matching against group patterns saved via -`SG <section3.3.1_>`_
  is attempted when -`PO <section5.1_>`_ (-PatternOffset) is present or the file is not yet in
  GDEXDB. Unmatched files default to group index 0 (no group).

  The number of values supplied to `Info <section5>`_ options must match the number of local
  file names, except for options that accept a single shared value: -`GI <section5.2_>`_, -`DF <section5.2_>`_,
  -`AF <section5.2_>`_, -`ST <section5.2_>`_ (-SavedFileType), and -`SP <section5.2_>`_.

  The storage location is set via -`LC <section5.2_>`_ (-Location). Defaults to 'G' (Glade
  Disk only).




:ref:`Back to Top <index>`
