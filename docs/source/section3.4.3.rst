
.. _section3.4.3:

3.4.3 - Set Web File Information
=====================


.. _SW:

Action Option -**SW** (-**SetWebFile**) (Alias: -**SetWeb**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates new or updates existing Web file
  records in GDEXDB for the specified dataset. Multiple records can be
  processed in a single run.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(SW|SetWebFile) [`Mode Options <mode_>`_]
|         [-(`WF|WebFile <section5.2_>`_) webFileNames]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`OB|OrderBy <section5.2_>`_) OrderByPattern]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|         [-(`GN|GroupName <section5.2_>`_) GroupNames]
|         [-(`TG|TopGroupIndex <section5.2_>`_) TopGroupIndices]
|         [-(`PO|PatternOffset <section5.1_>`_) PatternStringOffset]
|         [-(`WT|WebFileType <section5.2_>`_) WebFileTypes]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`FS|FileStatus <section5.2_>`_) WebFileStatus]
|         [-(`FF|FileFlag <section5.2_>`_) FilesOrPaths]
|         [-(`DF|DataFormat <section5.2_>`_) DataFormats]
|         [-(`AF|ArchiveFormat <section5.2_>`_) FileArchiveFormats]
|         [-(`DO|DisplayOrder <section5.2_>`_) DisplayOrderIndices]
|         [-(`SZ|Size <section5.2_>`_) FileSizes]
|         [-(`MC|MD5Checksum <section5.2_>`_) MD5ChecksumValues]
|         [-(`FD|FileDate <section5.2_>`_) DateModified]
|         [-(`FT|FileTime <section5.2_>`_) TimeModified]
|         [-(`ML|MetaLink <section5.2_>`_) MetadataLinks]
|         [-(`TL|ThreddLink <section5.2_>`_) ThreddCatalogLinks]
|         [-(`DE|Description <section5.2_>`_) WebFileDescriptions]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`AL|AsyncLimit <section5.1_>`_) AsyncProcessLimit]
|         [-(`QS|QsubOptions <section5.1_>`_)  PBSBatchOptions]
|         [-(`BP|BatchProcess <section5.2_>`_) [BatchControlInfo]]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4_>`_)
     - runs in background; suppresses screen output and errors
   * - -(`DX|DeleteXML <section4_>`_)
     - calls **dcm** to delete content metadata for the specified Web files
   * - -(`EM|EMailNotice <section4_>`_)
     - sends an email summary (including any errors) when the action completes or aborts
   * - -(`GX|GatherXML <section4_>`_)
     - calls **gatherxml** to evaluate file content metadata
   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NE|NoEmail <section4_>`_)
     - suppresses email notification on failure
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`RD|RemoveDir <section4_>`_)
     - removes empty web directories after file changes
   * - -(`RO|ResetOrder <section4_>`_)
     - resets display order indices to match the order files are given per -`WF <section5.2_>`_. Alternatively, use -`ON <section5.1_>`_ (-OrderNames) to reorder all files in the dataset and affected groups
   * - -(`RS|GXRSOptions <section4_>`_)
     - passes options R and S to **gatherxml** for faster processing, used with -`GX <section4_>`_ (-GatherXML)
   * - -(`SC|SetChecksum <section4_>`_)
     - computes MD5 checksums for files on the GDEX Server and saves them to GDEXDB

  Web file names must be provided via -`WF <section5.2_>`_ (-WebFile) unless -`ON <section5.1_>`_ (-OrderNames)
  is used to reorder files. The number of values supplied to other `Info <section5>`_ options
  must match the number of file names, except for options that accept a single
  shared value, such as -`GI <section5.2_>`_ (-GroupIndex), -`AF <section5.2_>`_ (-ArchiveFormat), -`DF <section5.2_>`_
  (-DataFormat), and -`WT <section5.2_>`_ (-WebFileType).

  If no group index is specified and -`PO <section5.1_>`_ (-PatternOffset) is present, file
  names are matched against group patterns saved via -`SG <section3.3.1_>`_ (-SetGroup) to
  determine the group index automatically.

  The file status may be set to P (public) or I (internal) for data types D,
  N, O, and S. Files assigned to an internal group are automatically set to I.




:ref:`Back to Top <index>`
