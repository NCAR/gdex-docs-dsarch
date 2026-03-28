
.. _section3.4.2:

3.4.2 - Get Saved File Information
=====================


.. _GS:

Action Option -**GS** (-**GetSavedFile**) (Alias: -**GetSaved**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves Saved file records from
GDEXDB for the specified dataset, optionally filtered by file name.

|  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(GS|GetSavedFile) [:ref:`Mode Options <mode3.4.2>`]
|             [:ref:`-(FN|FieldNames) <FN>` FieldNameString]
|             [:ref:`-(ON|OrderNames) <ON>` OrderNameString]
|             [:ref:`-(OB|OrderBy) <OB>` OrderByPattern]
|             [:ref:`-(SF|SavedFile) <SF>` SavedFileNames]
|             [:ref:`-(ST|SavedFileType) <ST>` SavedFileTypes]
|             [:ref:`-(FS|FileStatus) <FS>` SavedFileStatus]
|             [:ref:`-(FF|FileFlag) <FF>` FilesOrPaths]
|             [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|             [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|             [:ref:`-(GN|GroupName) <GN>` GroupNames]
|             [:ref:`-(TG|TopGroupIndex) <TG>` TopGroupIndices]
|             [:ref:`-(DE|Description) <DE>` SavedFileDescriptions]
|             [:ref:`-(OF|OutputFile) <OF>` OutputFileName]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.2:

:ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FO|FormatOutput) <FO>`
     - formats each column to a uniform fixed width
   * - :ref:`-(RG|RecursiveGroup) <RG>`
     - gathers files in subgroups recursively for a given group index
   * - :ref:`-(RN|RelativeName) <RN>`
     - returns file names with paths relative to the Saved path of the dataset or group

Use :ref:`-FN <FN>` (-FieldNames) to specify which Saved file fields to retrieve. Defaults
to 'FINMTHS'. Use :ref:`-FN <FN>` ALL for all available fields.

Valid Saved file field names and their corresponding :ref:`Info options <section5>`:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - F
     - :ref:`-(SF|SavedFile) <SF>`
     - Saved file names with relative paths
   * - T
     - :ref:`-(ST|SavedFileType) <ST>`
     - Saved file archiving types
   * - C
     - :ref:`-(MC|MD5Checksum) <MC>`
     - Saved file MD5 Checksum
   * - I
     - :ref:`-(GI|GroupIndex) <GI>`
     - group indices for Saved files
   * - X
     - :ref:`-(TG|TopGroupIndex) <TG>`
     - top group indices for Saved files
   * - V
     - :ref:`-(VI|VersionIndex) <VI>`
     - Version control index
   * - N
     - :ref:`-(DF|DataFormat) <DF>`
     - data content formats
   * - M
     - :ref:`-(AF|ArchiveFormat) <AF>`
     - file archive formats
   * - O
     - :ref:`-(DO|DisplayOrder) <DO>`
     - display order indices
   * - B
     - :ref:`-(QF|QuasarFile) <QF>`
     - Quasar backup file names
   * - Q
     - :ref:`-(QT|QuasarType) <QT>`
     - Quasar backup file types
   * - L
     - :ref:`-(LC|Location) <LC>`
     - Saved file storage location flag
   * - H
     - :ref:`-(FS|FileStatus) <FS>`
     - Saved file archiving status
   * - P
     - :ref:`-(FF|FileFlag) <FF>`
     - File type flag, File or Path
   * - S
     - :ref:`-(SZ|Size) <SZ>`
     - Saved file sizes
   * - J
     - :ref:`-(FD|FileDate) <FD>`
     - date data last modified on
   * - K
     - :ref:`-(FT|FileTime) <FT>`
     - time data last modified at
   * - D
     - :ref:`-(DE|Description) <DE>`
     - Saved file descriptions

A dataset number is required unless Saved file names are provided. If file
names match multiple datasets and no dataset number is given, an error prompts
the specialist to specify one and rerun. Incomplete file paths are expanded
relative to the dataset Saved Home Directory.

Results can be filtered by archive type (:ref:`-ST <ST>`), group (:ref:`-GI <GI>` or :ref:`-GN <GN>`), and
description (:ref:`-DE <DE>`). The :ref:`-SF <SF>`, :ref:`-GN <GN>`, and :ref:`-DE <DE>` options accept the '%' wildcard.




:ref:`Back to Top <index>`
