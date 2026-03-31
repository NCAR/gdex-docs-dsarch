
.. _section3.4.7:

3.4.7 - Set Quasar File Information
===================================


.. _SQ:

Action Option -**SQ** (-**SetQuasarFile**) (Aliases: -**SetQuasar**, -**SetBackupFile**, -**SetBackup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

updates Quasar backup file records
in GDEXDB for the specified dataset. Multiple records can be processed per
execution.

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN [-](SQ|SetQuasarFile) [:ref:`Mode Options <mode3.4.7>`]
|           [:ref:`-(QF|QuasarFile) <QF>` QuasarFileNames]
|           [:ref:`-(ON|OrderNames) <ON>` OrderNameString]
|           [:ref:`-(OB|OrderBy) <OB>` OrderByPattern]
|           [:ref:`-(QT|QuasarFileType) <QT>` QuasarFileTypes]
|           [:ref:`-(BS|BackupStatus) <BS>` QuasarBackupFileStatus]
|           [:ref:`-(DF|DataFormat) <DF>` FileContentFormat]
|           [:ref:`-(AF|ArchiveFormat) <AF>` FileArchiveFormat]
|           [:ref:`-(DO|DisplayOrder) <DO>` DisplayOrderIndices]
|           [:ref:`-(SZ|Size) <SZ>` FileSizes]
|           [:ref:`-(MC|MD5Checksum) <MC>` MD5ChecksumValues]
|           [:ref:`-(FD|FileDate) <FD>` DateModified]
|           [:ref:`-(FT|FileTime) <FT>` TimeModified]
|           [:ref:`-(DE|Description) <DE>` SavedFileDescriptions]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|           [:ref:`-(BP|BatchProcess) <BP>` [BatchControlInfo]]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.7:

:ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(BG|BackGround) <BG>`
     - runs in background; suppresses screen output and errors
   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NE|NoEmail) <NE>`
     - suppresses email notification on failure
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(RO|ResetOrder) <RO>`
     - resets display order indices to match the order files are given per :ref:`-QF <QF>`. Alternatively, use :ref:`-ON <ON>` (-OrderNames) to reorder all files in the dataset
   * - :ref:`-(SC|SetChecksum) <SC>`
     - computes MD5 checksums for files on the GDEX Server and saves them to GDEXDB

Quasar file names must be provided via :ref:`-QF <QF>` (-QuasarFile) unless :ref:`-ON <ON>`
(-OrderNames) is used to reorder files. The number of values supplied to other
:ref:`Info options <section5>` must match the number of file names, except for options that
accept a single shared value, such as :ref:`-AF <AF>`, :ref:`-DF <DF>`, and :ref:`-QT <QT>` (-QuasarFileType).



| :ref:`Back to Top <section3.4.7>`
| :ref:`Back to Table of Contents <index>`
