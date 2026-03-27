
.. _section3.4.5:

3.4.5 - Set Help File Information
=====================


.. _SH:

Action Option -**SH** (-**SetHelpFile**) (Alias: -**SetHelp**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates new or updates existing Help
  file records (Documents and Software) in GDEXDB for the specified dataset.
  Multiple records can be processed in a single run.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN -(SH|SetHelpFile) [:ref:`Mode Options <mode3.4.5>`]
|           [-(:ref:`HF|HelpFile <HF>`) HelpFileNames]
|           [-(:ref:`WU|WebURL <WU>`) RemoteFileWebURL]
|           [-(:ref:`SR|Source <SR>`) ContributionSource]
|           [-(:ref:`ON|OrderNames <ON>`) OrderNameString]
|           [-(:ref:`OB|OrderBy <OB>`) OrderByPattern]
|           [-(:ref:`HT|HelpFileType <HT>`) HelpFileTypes]
|           [-(:ref:`FS|FileStatus <FS>`) HelpFileStatus]
|           [-(:ref:`FF|FileFlag <FF>`) FilesOrPaths]
|           [-(:ref:`LC|Location <LC>`) StorageLocationFlags]
|           [-(:ref:`DF|DataFormat <DF>`) DataFormats]
|           [-(:ref:`AF|ArchiveFormat <AF>`) FileArchiveFormats]
|           [-(:ref:`DO|DisplayOrder <DO>`) DisplayOrderIndices]
|           [-(:ref:`SZ|Size <SZ>`) FileSizes]
|           [-(:ref:`MC|MD5Checksum <MC>`) MD5ChecksumValues]
|           [-(:ref:`ID|InitialDate <ID>`) HelpFileInitialDate]
|           [-(:ref:`FD|FileDate <FD>`) DateModified]
|           [-(:ref:`FT|FileTime <FT>`) TimeModified]
|           [-(:ref:`DE|Description <DE>`) SavedFileDescriptions]
|           [-(:ref:`LN|LoginName <LN>`) LoginAccountName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.4.5:

  :ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - \-(:ref:`BG|BackGround <BG>`)
     - runs in background; suppresses screen output and errors
   * - \-(:ref:`EM|EMailNotice <EM>`)
     - sends an email summary (including any errors) when the action completes or aborts
   * - \-(:ref:`MD|MyDataset <MD>`)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - \-(:ref:`NE|NoEmail <NE>`)
     - suppresses email notification on failure
   * - \-(:ref:`NT|NoTrim <NT>`)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - \-(:ref:`RO|ResetOrder <RO>`)
     - resets display order indices to match the order files are provided
   * - \-(:ref:`SC|SetChecksum <SC>`)
     - computes MD5 checksums for Help files and saves them to GDEXDB

  Help file names must be provided via -:ref:`HF <HF>` (-HelpFile) unless -:ref:`ON <ON>` (-OrderNames)
  is used to reorder files. The number of values supplied to other :ref:`Info <section5>` options
  must match the number of file names, except for options that accept a single
  shared value, such as -:ref:`AF <AF>`, -:ref:`DF <DF>`, and -:ref:`HT <HT>` (-HelpFileType).

  For remotely hosted Help files (e.g., on GitHub), provide the full URL via
  -:ref:`WU <WU>` (-WebURL) to add a record without a local copy on the GDEX Server.




:ref:`Back to Top <index>`
