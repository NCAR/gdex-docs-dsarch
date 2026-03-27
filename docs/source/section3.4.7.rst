
.. _section3.4.7:

3.4.7 - Set Quasar File Information
=====================


.. _SQ:

Action Option -**SQ** (-**SetQuasarFile**) (Aliases: -**SetQuasar**, -**SetBackupFile**, -**SetBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

updates Quasar backup file records
  in GDEXDB for the specified dataset. Multiple records can be processed per
  execution.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](SQ|SetQuasarFile) [`Mode Options <mode_>`_]
|         [-(`QF|QuasarFile <section5.2_>`_) QuasarFileNames]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`OB|OrderBy <section5.2_>`_) OrderByPattern]
|         [-(`QT|QuasarFileType <section5.2_>`_) QuasarFileTypes]
|         [-(`BS|BackupStatus <section5.2_>`_) QuasarBackupFileStatus]
|         [-(`DF|DataFormat <section5.2_>`_) FileContentFormat]
|         [-(`AF|ArchiveFormat <section5.2_>`_) FileArchiveFormat]
|         [-(`DO|DisplayOrder <section5.2_>`_) DisplayOrderIndices]
|         [-(`SZ|Size <section5.2_>`_) FileSizes]
|         [-(`MC|MD5Checksum <section5.2_>`_) MD5ChecksumValues]
|         [-(`FD|FileDate <section5.2_>`_) DateModified]
|         [-(`FT|FileTime <section5.2_>`_) TimeModified]
|         [-(`DE|Description <section5.2_>`_) SavedFileDescriptions]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`QS|QsubOptions <section5.1_>`_)  PBSBatchOptions]
|         [-(`BP|BatchProcess <section5.2_>`_) [BatchControlInfo]]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4_>`_)
     - runs in background; suppresses screen output and errors
   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NE|NoEmail <section4_>`_)
     - suppresses email notification on failure
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`RO|ResetOrder <section4_>`_)
     - resets display order indices to match the order files are given per -`QF <section5.2_>`_. Alternatively, use -`ON <section5.1_>`_ (-OrderNames) to reorder all files in the dataset
   * - -(`SC|SetChecksum <section4_>`_)
     - computes MD5 checksums for files on the GDEX Server and saves them to GDEXDB

  Quasar file names must be provided via -`QF <section5.2_>`_ (-QuasarFile) unless -`ON <section5.1_>`_
  (-OrderNames) is used to reorder files. The number of values supplied to other
  `Info <section5>`_ options must match the number of file names, except for options that
  accept a single shared value, such as -`AF <section5.2_>`_, -`DF <section5.2_>`_, and -`QT <section5.2_>`_ (-QuasarFileType).




:ref:`Back to Top <index>`
