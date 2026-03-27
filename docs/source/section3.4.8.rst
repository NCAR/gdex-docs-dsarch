
.. _section3.4.8:

3.4.8 - Get Quasar File Information
=====================


.. _GQ:

Action Option -**GQ** (-**GetQuasarFile**) (Aliases: -**GetQuasar**, -**GetBackupFile**, -**GetBackup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves Quasar backup file records
  from GDEXDB for the specified dataset, optionally filtered by file name.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN -(GQ|GetQuasarFile) [:ref:`Mode Options <mode3.4.8>`]
|           [-(:ref:`FN|FieldNames <FN>`) FieldNameString]
|           [-(:ref:`ON|OrderNames <ON>`) OrderNameString]
|           [-(:ref:`OB|OrderBy <OB>`) OrderByPattern]
|           [-(:ref:`QF|QuasarFile <QF>`) QuasarFileNames]
|           [-(:ref:`QT|QuasarFileType <QT>`) QuasarFileTypes]
|           [-(:ref:`FS|FileStatus <FS>`) QuasarFileStatus]
|           [-(:ref:`DE|Description <DE>`) QuasarFileDescriptions]
|           [-(:ref:`OF|OutputFile <OF>`) OutputFileName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.4.8:

  :ref:`Mode option <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - \-(:ref:`FO|FormatOutput <FO>`)
     - formats each column to a uniform fixed width

  Use -:ref:`FN <FN>` (-FieldNames) to specify which Quasar file fields to retrieve. Defaults
  to 'FNMTHS'. Use -:ref:`FN <FN>` ALL for all available fields.

  Valid Quasar file field names and their corresponding :ref:`Info options <section5>`:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - F
     - \-(:ref:`QF|QuasarFile <QF>`)
     - Quasar file names with relative paths
   * - T
     - \-(:ref:`QT|QuasarFileType <QT>`)
     - Quasar file archiving types
   * - C
     - \-(:ref:`MC|MD5Checksum <MC>`)
     - Saved file MD5 Checksum
   * - N
     - \-(:ref:`DF|DataFormat <DF>`)
     - data content formats
   * - M
     - \-(:ref:`AF|ArchiveFormat <AF>`)
     - file archive formats
   * - O
     - \-(:ref:`DO|DisplayOrder <DO>`)
     - display order indices
   * - B
     - \-(:ref:`QF|QuasarFile <QF>`)
     - Quasar backup file names
   * - Q
     - \-(:ref:`QT|QuasarType <QT>`)
     - Quasar backup file types
   * - H
     - \-(:ref:`FS|FileStatus <FS>`)
     - Quasar file archiving status
   * - S
     - \-(:ref:`SZ|Size <SZ>`)
     - Quasar file sizes
   * - J
     - \-(:ref:`FD|FileDate <FD>`)
     - date data last modified on
   * - K
     - \-(:ref:`FT|FileTime <FT>`)
     - time data last modified at
   * - D
     - \-(:ref:`DE|Description <DE>`)
     - Quasar file descriptions

  A dataset number is required unless Quasar file names are provided. If file
  names match multiple datasets and no dataset number is given, an error prompts
  the specialist to specify one and rerun. Incomplete file paths are expanded
  relative to the dataset Home Directory.

  Results can be filtered by archive type (-:ref:`QT <QT>`) and description (-:ref:`DE <DE>`). Both
  -:ref:`QF <QF>` and -:ref:`DE <DE>` accept the '%' wildcard.




:ref:`Back to Top <index>`
