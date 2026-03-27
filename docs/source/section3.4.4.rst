
.. _section3.4.4:

3.4.4 - Get Web File Information
=====================


.. _GW:

Action Option -**GW** (-**GetWebFile**) (Alias: -**GetWeb**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves Web file records from GDEXDB
  for the specified dataset, optionally filtered by file name.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN -(GW|GetWebFile) [:ref:`Mode Options <mode3.4.4>`]
|           [-(:ref:`FN|FieldNames <FN>`) FieldNameString]
|           [-(:ref:`ON|OrderNames <ON>`) OrderNameString]
|           [-(:ref:`OB|OrderBy <OB>`) OrderByPattern]
|           [-(:ref:`WF|WebFile <WF>`) WebFileNames]
|           [-(:ref:`WT|WebFileType <WT>`) WebFileTypes]
|           [-(:ref:`FS|FileStatus <FS>`) WebFileStatus]
|           [-(:ref:`FF|FileFlag <FF>`) FilesOrPaths]
|           [-(:ref:`LC|Location <LC>`) StorageLocationFlags]
|           [-(:ref:`GI|GroupIndex <GI>`) GroupIndices]
|           [-(:ref:`GN|GroupName <GN>`) GroupNames]
|           [-(:ref:`TG|TopGroupIndex <TG>`) TopGroupIndices]
|           [-(:ref:`DE|Description <DE>`) WebFileDescriptions]
|           [-(:ref:`OF|OutputFile <OF>`) OutputFileName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.4.4:

  :ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - \-(:ref:`FO|FormatOutput <FO>`)
     - formats each column to a uniform fixed width
   * - \-(:ref:`RG|RecursiveGroup <RG>`)
     - gathers files in subgroups recursively for a given group index
   * - \-(:ref:`RN|RelativeName <RN>`)
     - returns file names with paths relative to the Web path of the dataset or group

  Use -:ref:`FN <FN>` (-FieldNames) to specify which Web file fields to retrieve. Defaults
  to 'FINMTHS'. Use -:ref:`FN <FN>` ALL for all available fields.

  Valid Web file field names and their corresponding :ref:`Info options <section5>`:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - F
     - \-(:ref:`WF|WebFile <WF>`)
     - Web file names with relative paths
   * - T
     - \-(:ref:`WT|WebFileType <WT>`)
     - Web file archiving types
   * - C
     - \-(:ref:`MC|MD5Checksum <MC>`)
     - Web file MD5 Checksum
   * - I
     - \-(:ref:`GI|GroupIndex <GI>`)
     - group indices for Web files
   * - X
     - \-(:ref:`TG|TopGroupIndex <TG>`)
     - top group indices for Web files
   * - V
     - \-(:ref:`VI|VersionIndex <VI>`)
     - Version control index
   * - M
     - \-(:ref:`AF|ArchiveFormat <AF>`)
     - file archive formats
   * - N
     - \-(:ref:`DF|DataFormat <DF>`)
     - data content formats
   * - O
     - \-(:ref:`DO|DisplayOrder <DO>`)
     - display order indices
   * - B
     - \-(:ref:`QF|QuasarFile <QF>`)
     - Quasar backup file names
   * - Q
     - \-(:ref:`QT|QuasarType <QT>`)
     - Quasar backup file types
   * - L
     - \-(:ref:`LC|Location <LC>`)
     - Web file storage location flag
   * - H
     - \-(:ref:`FS|FileStatus <FS>`)
     - Web file archiving status
   * - P
     - \-(:ref:`FF|FileFlag <FF>`)
     - File type flag, File or Path
   * - S
     - \-(:ref:`SZ|Size <SZ>`)
     - Web file sizes
   * - J
     - \-(:ref:`FD|FileDate <FD>`)
     - date data last modified on
   * - K
     - \-(:ref:`FT|FileTime <FT>`)
     - time data last modified at
   * - A
     - \-(:ref:`ML|MetaLink <ML>`)
     - a link to content meta at the file level
   * - E
     - \-(:ref:`TL|ThreddLink <TL>`)
     - a link to Thredd Catalog page at the file level
   * - D
     - \-(:ref:`DE|Description <DE>`)
     - Web file descriptions

  A dataset number is required unless Web file names are provided. If file
  names match multiple datasets and no dataset number is given, an error prompts
  the specialist to specify one and rerun. Incomplete file paths are expanded
  relative to the dataset Web Home Directory.

  Results can be filtered by archive type (-:ref:`WT <WT>`), group (-:ref:`GI <GI>` or -:ref:`GN <GN>`), and
  description (-:ref:`DE <DE>`). The -:ref:`WF <WF>`, -:ref:`GN <GN>`, and -:ref:`DE <DE>` options accept the '%' wildcard.


.. _3.4.4_e10:

**EXAMPLE 10. To retrieve the default Web file fields for d540000, filtered to Data type and file names containing '200':**

| **dsarch** d540000 :ref:`GW <GW>` -:ref:`WT <WT>` D -:ref:`WF <WF>` %200%

Content of the output:

.. code-block:: none

   Dataset<=>d540000
   WebFile<:>GroupIndex<:>DataFormat<:>ArchiveFormat<:>WebFileType<:>Size<:>
   IMMA_2.4_1998_2000.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1283094016<:>
   IMMA_2.4_2001_2002.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1006424064<:>
   IMMA_2.4_2003_2004.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1149672960<:>
   IMMA_2.4_2005.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>951742976<:>
   IMMA_2.4_2006.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1119821824<:>
   IMMA_2.4_2007.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>656820224<:>




:ref:`Back to Top <index>`
