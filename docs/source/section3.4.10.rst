
.. _section3.4.10:

3.4.10 - Archive Web Files
=====================


.. _AW:

Action Option -**AW** (-**ArchiveWebFile**) (Aliases: -**ArchiveWeb**, -**ArchWeb**, -**ArchWebFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

copies
local files to the GDEX Server as publicly accessible Web files and registers
them in GDEXDB. One or more files may be archived per execution.

|  **dsarch** [:ref:`-(DS|dataset) <DS>`] dNNNNNN -(AW|ArchiveWebFile) [:ref:`Mode Options <mode3.4.10>`]
|             [:ref:`-(LF|LocalFile) <LF>` LocalFileNames]
|             [:ref:`-(LD|LocalDirectory) <LD>` LocalDirectoryName]
|             [:ref:`-(LL|LocalFileList) <LL>` LocalFileListName]
|             [:ref:`-(WF|WebFile) <WF>` webFileNames]
|             [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|             [:ref:`-(TG|TopGroupIndex) <TG>` TopGroupIndices]
|             [:ref:`-(GN|GroupName) <GN>` GroupNames]
|             [:ref:`-(PO|PatternOffset) <PO>` PatternStringOffset]
|             [:ref:`-(WT|WebFileType) <WT>` WebFileTypes]
|             [:ref:`-(FS|FileStatus) <FS>` WebFileStatus]
|             [:ref:`-(FF|FileFlag) <FF>` FilesOrPaths]
|             [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|             [:ref:`-(DF|DataFormat) <DF>` DataFormat]
|             [:ref:`-(AF|ArchiveFormat) <AF>` FileArchiveFormat]
|             [:ref:`-(DO|DisplayOrder) <DO>` DisplayOrderIndices]
|             [:ref:`-(SZ|Size) <SZ>` FileSizes]
|             [:ref:`-(MC|MD5Checksum) <MC>` MD5ChecksumValues]
|             [:ref:`-(DE|Description) <DE>` WebFileDescriptions]
|             [:ref:`-(VS|ValidSize) <VS>` MinSizeForValidFile]
|             [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|             [:ref:`-(AL|AsyncLimit) <AL>` AsyncProcessLimit]
|             [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|             [:ref:`-(BP|BatchProcess) <BP>` [BatchControlInfo]]
|             [:ref:`-(DD|DeleteDir) <DD>` DeleteLocalDirLevel]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.10:

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
   * - :ref:`-(GX|GatherXML) <GX>`
     - calls **gatherxml** to evaluate file content metadata directly from the local file
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
     - overwrites existing Web files
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets display order indices to match the order files are given per -:ref:`WF <WF>`. Alternatively, use -:ref:`ON <ON>` (-OrderNames) to reorder all files in the dataset and affected groups
   * - :ref:`-(SC|SetChecksum) <SC>`
     - computes MD5 checksums for files on the GDEX Server and saves them to GDEXDB
   * - :ref:`-(UZ|UnzipData) <UZ>`
     - decompresses files using 'gunzip', 'uncompress', 'unzip', or 'bunzip' according to the extension: '.gz', '.Z', '.zip', or '.bz2', respectively
   * - :ref:`-(XC|CrossCopy) <XC>`
     - copies files from existing Web/Object storage to fill missing Object/Web copies, using GDEXDB records for guidance
   * - :ref:`-(XM|CrossMove) <XM>`
     - moves files from existing Web/Object storage to fill missing Object/Web copies (originals are removed)
   * - :ref:`-(ZD|ZipData) <ZD>`
     - compresses files using 'gzip', 'compress', 'zip', or 'bzip' according to the archive format ('GZ', 'Z', 'ZIP', or 'BZ2') given via -:ref:`AF <AF>` (-ArchiveFormat)

Local file names are provided via -:ref:`LF <LF>` (-LocalFile). On the command line,
'*' and '?' wildcards are supported. Files not in the current directory must
include relative or absolute paths. If a directory is given via -:ref:`LD <LD>`
(-LocalDirectory), files are gathered recursively from that tree.

Local file names are used as Web file names by default unless -:ref:`WF <WF>` (-WebFile)
is given explicitly. Files are archived under the dataset home directory;
use -:ref:`WP <WP>` (-WebPath) or the path stored in GDEXDB to override. When -:ref:`KP <KP>`
(-KeepLocalPath) is specified, local file paths are used as-is and -:ref:`WP <WP>` is
not permitted.

Assign files to a group via -:ref:`GI <GI>` (-GroupIndex) or -:ref:`GN <GN>` (-GroupName). If no
group is specified, pattern matching against group patterns saved via -:ref:`SG <SG>`
is attempted when -:ref:`PO <PO>` (-PatternOffset) is present or the file is not yet in
GDEXDB. Unmatched files default to group index 0.

Web files may be archived as P (public) or I (internal) for data types D or
N. Files assigned to an internal group are automatically set to I.

The number of values supplied to :ref:`Info options <section5>` must match the number of local
file names, except for options that accept a single shared value: -:ref:`GI <GI>`, -:ref:`DF <DF>`,
-:ref:`AF <AF>`, -:ref:`WT <WT>` (-WebFileType), and -:ref:`WP <WP>`.

The storage location is set via -:ref:`LC <LC>` (-Location). Defaults to 'G' (Glade
Disk only).




:ref:`Back to Top <index>`
