
.. _section3.4.11:

3.4.11 - Archive Help Files
=====================


.. _AH:

Action Option -**AH** (-**ArchiveHelpFile**) (Aliases: -**ArchiveHelp**, -**ArchHelp**, -**ArchHelpFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -ArchiveHelp|-ArchHelp|-ArchHelpFile),
copies local files to the GDEX Server as Help files (Documents and Software)
and registers them in GDEXDB. One or more files may be archived per execution.

|  **dsarch** [:ref:`-(DS|dataset) <DS>`] dNNNNNN -(AH|ArchiveHelpFile) [:ref:`Mode Options <mode3.4.11>`]
|             :ref:`-(LF|LocalFile) <LF>` LocalFileNames
|             [:ref:`-(HF|HelpFile) <HF>` HelpFileNames]
|             [:ref:`-(HT|HelpFileType) <HT>` HelpFileTypes]
|             [:ref:`-(FS|FileStatus) <FS>` HelpFileStatus]
|             [:ref:`-(FF|FileFlag) <FF>` FilesOrPaths]
|             [:ref:`-(DF|DataFormat) <DF>` FileContentFormat]
|             [:ref:`-(AF|ArchiveFormat) <AF>` FileArchiveFormat]
|             [:ref:`-(DO|DisplayOrder) <DO>` DisplayOrderIndices]
|             [:ref:`-(SZ|Size) <SZ>` FileSizes]
|             [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|             [:ref:`-(MC|MD5Checksum) <MC>` MD5ChecksumValues]
|             [:ref:`-(DE|Description) <DE>` SavedFileDescriptions]
|             [:ref:`-(VS|ValidSize) <VS>` MinSizeForValidFile]
|             [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|             [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|             [:ref:`-(BP|BatchProcess) <BP>` [BatchControlInfo]]
|             [:ref:`-(DD|DeleteDir) <DD>` DeleteLocalDirLevel]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.11:

:ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(BG|BackGround) <BG>`
     - runs in background; suppresses screen output and errors
   * - :ref:`-(CL|CleanLocal) <CL>`
     - removes local files after all are successfully archived
   * - :ref:`-(EM|EMailNotice) <EM>`
     - sends an email summary (including any errors) when the action completes or aborts
   * - :ref:`-(GZ|GMTZone) <GZ>`
     - uses GMT rather than local time for archiving timestamps
   * - :ref:`-(KP|KeepLocalPath) <KP>`
     - uses local file paths as relative paths on the GDEX Server
   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NE|NoEmail) <NE>`
     - suppresses email notification on failure
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(OE|OverrideExist) <OE>`
     - overwrites existing Help files
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets display order indices to match the order files are given per :ref:`-HF <HF>`. Alternatively, use :ref:`-ON <ON>` (-OrderNames) to reorder all files in the dataset and affected groups
   * - :ref:`-(SC|SetChecksum) <SC>`
     - computes MD5 checksums for Help files and saves them to GDEXDB

Local file names are provided via :ref:`-LF <LF>` (-LocalFile). On the command line,
'*' and '?' wildcards are supported. Files not in the current directory must
include relative or absolute paths. If a directory is given via :ref:`-LD <LD>`
(-LocalDirectory), files are gathered recursively.

Local file names are used as Help file names by default unless :ref:`-HF <HF>` (-HelpFile)
is given explicitly. When :ref:`-KP <KP>` (-KeepLocalPath) is specified, local file paths
are used as-is on the GDEX Server.

The number of values supplied to :ref:`Info options <section5>` must match the number of local
file names, except for options that accept a single shared value: :ref:`-DF <DF>`, :ref:`-AF <AF>`,
and :ref:`-HT <HT>` (-HelpFileType).

The storage location is set via :ref:`-LC <LC>` (-Location). Defaults to 'B' (both Web
Disk and Object Store).




:ref:`Back to Top <index>`
