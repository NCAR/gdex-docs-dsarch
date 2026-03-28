
.. _section3.4.1:

3.4.1 - Set Saved File Information
=====================


.. _SS:

Action Option -**SS** (-**SetSavedFile**) (Alias: -**SetSaved**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates new or updates existing
Saved file records in GDEXDB for the specified dataset. Multiple records
can be processed in a single run.

|  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN [-](SS|SetSavedFile) [:ref:`Mode Options <mode3.4.1>`]
|             [:ref:`-(SF|SavedFile) <SF>` SavedFileNames]
|             [:ref:`-(ON|OrderNames) <ON>` OrderNameString]
|             [:ref:`-(OB|OrderBy) <OB>` OrderByPattern]
|             [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|             [:ref:`-(GN|GroupName) <GN>` GroupNames]
|             [:ref:`-(TG|TopGroupIndex) <TG>` TopGroupIndices]
|             [:ref:`-(PO|PatternOffset) <PO>` PatternStringOffset]
|             [:ref:`-(ST|SavedFileType) <ST>` SavedFileTypes]
|             [:ref:`-(FS|FileStatus) <FS>` SavedFileStatus]
|             [:ref:`-(FF|FileFlag) <FF>` FilesOrPaths]
|             [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|             [:ref:`-(DF|DataFormat) <DF>` DataFormats]
|             [:ref:`-(AF|ArchiveFormat) <AF>` FileArchiveFormats]
|             [:ref:`-(DO|DisplayOrder) <DO>` DisplayOrderIndices]
|             [:ref:`-(SZ|Size) <SZ>` FileSizes]
|             [:ref:`-(MC|MD5Checksum) <MC>` MD5ChecksumValues]
|             [:ref:`-(FD|FileDate) <FD>` DateModified]
|             [:ref:`-(FT|FileTime) <FT>` TimeModified]
|             [:ref:`-(DE|Description) <DE>` SavedFileDescriptions]
|             [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|             [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|             [:ref:`-(BP|BatchProcess) <BP>` [BatchControlInfo]]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.1:

:ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(BG|BackGround) <BG>`
     - runs in background; suppresses screen output and errors
   * - :ref:`-(EM|EMailNotice) <EM>`
     - sends an email summary (including any errors) when the action completes or aborts
   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NE|NoEmail) <NE>`
     - suppresses email notification on failure
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(RD|RemoveDir) <RD>`
     - removes empty directories after file changes
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets display order indices to match the order files are given per :ref:`-SF <SF>`. Alternatively, use :ref:`-ON <ON>` (-OrderNames) to reorder all files in the dataset and affected groups
   * - :ref:`-(SC|SetChecksum) <SC>`
     - computes MD5 checksums for files on the GDEX Server and saves them to GDEXDB

Saved file names must be provided via :ref:`-SF <SF>` (-SavedFile) unless :ref:`-ON <ON>`
(-OrderNames) is used to reorder files. The number of values supplied to
other :ref:`Info options <section5>` must match the number of file names, except for options
that accept a single shared value, such as :ref:`-GI <GI>` (-GroupIndex), :ref:`-AF <AF>`
(-ArchiveFormat), :ref:`-DF <DF>` (-DataFormat), and :ref:`-ST <ST>` (-SavedFileType).

If no group index is specified and :ref:`-PO <PO>` (-PatternOffset) is present, file
names are matched against group patterns saved via :ref:`-SG <SG>` (-SetGroup) to
determine the group index automatically.



:ref:`Back to Top <section3.4.1>`
:ref:`Back to Table of Contents <index>`

