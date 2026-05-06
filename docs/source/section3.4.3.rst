
.. _section3.4.3:

3.4.3 - Set Web File Information
=================================


.. _SW:

Action Option -**SW** (-**SetWebFile**) (Alias: -**SetWeb**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates new or updates existing
Web file records in GDEXDB for the specified dataset. Multiple
records can be processed in a single run.

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(SW|SetWebFile) [:ref:`Mode Options <mode3.4.3>`]
|           [:ref:`-(WF|WebFile) <WF>` webFileNames]
|           [:ref:`-(ON|OrderNames) <ON>` OrderNameString]
|           [:ref:`-(OB|OrderBy) <OB>` OrderByPattern]
|           [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|           [:ref:`-(GN|GroupName) <GN>` GroupNames]
|           [:ref:`-(TG|TopGroupIndex) <TG>` TopGroupIndices]
|           [:ref:`-(PO|PatternOffset) <PO>` PatternStringOffset]
|           [:ref:`-(WT|WebFileType) <WT>` WebFileTypes]
|           [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|           [:ref:`-(FS|FileStatus) <FS>` WebFileStatus]
|           [:ref:`-(FF|FileFlag) <FF>` FilesOrPaths]
|           [:ref:`-(DF|DataFormat) <DF>` DataFormats]
|           [:ref:`-(AF|ArchiveFormat) <AF>` FileArchiveFormats]
|           [:ref:`-(DO|DisplayOrder) <DO>` DisplayOrderIndices]
|           [:ref:`-(SZ|Size) <SZ>` FileSizes]
|           [:ref:`-(MC|MD5Checksum) <MC>` MD5ChecksumValues]
|           [:ref:`-(FD|FileDate) <FD>` DateModified]
|           [:ref:`-(FT|FileTime) <FT>` TimeModified]
|           [:ref:`-(ML|MetaLink) <ML>` MetadataLinks]
|           [:ref:`-(TL|ThreddLink) <TL>` ThreddCatalogLinks]
|           [:ref:`-(DE|Description) <DE>` WebFileDescriptions]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(AL|AsyncLimit) <AL>` AsyncProcessLimit]
|           [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|           [:ref:`-(BP|BatchProcess) <BP>` [BatchControlInfo]]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(BG|BackGround) <BG>`
     - runs in background; suppresses screen output and errors
   * - :ref:`-(DX|DeleteXML) <DX>`
     - calls **dcm** to delete content metadata for the specified Web files
   * - :ref:`-(EM|EMailNotice) <EM>`
     - sends an email summary (including any errors) when the action completes or aborts
   * - :ref:`-(GX|GatherXML) <GX>`
     - calls **gatherxml** to evaluate file content metadata
   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NE|NoEmail) <NE>`
     - suppresses email notification on failure
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(RD|RemoveDir) <RD>`
     - removes empty web directories after file changes
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets display order indices to match the order files are given per :ref:`-WF <WF>`. Alternatively, use :ref:`-ON <ON>` (-OrderNames) to reorder all files in the dataset and affected groups
   * - :ref:`-(RS|GXRSOptions) <RS>`
     - passes options R and S to **gatherxml** for faster processing, used with :ref:`-GX <GX>` (-GatherXML)
   * - :ref:`-(SC|SetChecksum) <SC>`
     - computes MD5 checksums for files on the GDEX Server and saves them to GDEXDB
   * - :ref:`-(WS|WithFileSize) <WS>`
     - gathers file size information for Web files on the GDEX Server and saves them to GDEXDB

Web file names must be provided via :ref:`-WF <WF>` (-WebFile) unless :ref:`-ON <ON>`
(-OrderNames) is used to reorder files. The number of values supplied
to other :ref:`Info options <section5>` must match the number of file names, except
for options that accept a single shared value, such as :ref:`-GI <GI>`
(-GroupIndex), :ref:`-AF <AF>` (-ArchiveFormat), :ref:`-DF <DF>` (-DataFormat), and :ref:`-WT <WT>`
(-WebFileType).

If no group index is specified and :ref:`-PO <PO>` (-PatternOffset) is present,
file names are matched against group patterns saved via :ref:`-SG <SG>`
(-SetGroup) to determine the group index automatically.

The file status may be set to P (public) or I (internal) for data
types D, N, O, and S. Files assigned to an internal group are
automatically set to I.



| :ref:`Back to Top <section3.4.3>`
| :ref:`Back to Table of Contents <index>`
