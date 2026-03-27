
.. _section3.4.6:

3.4.6 - Get Help File Information
=====================


.. _GH:

Action Option -**GH** (-**GetHelpFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves Help file records (Documents
  and Software) from GDEXDB for the specified dataset, optionally filtered by
  file name.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN -(GH|GetHelpFile) [:ref:`Mode Options <mode3.4.6>`]
|           [-(:ref:`FN|FieldNames <FN>`) FieldNameString]
|           [-(:ref:`ON|OrderNames <ON>`) OrderNameString]
|           [-(:ref:`OB|OrderBy <OB>`) OrderByPattern]
|           [-(:ref:`HF|HelpFile <HF>`) HelpFileNames]
|           [-(:ref:`HT|HelpFileType <HT>`) HelpFileTypes]
|           [-(:ref:`FS|FileStatus <FS>`) SavedFileStatus]
|           [-(:ref:`FF|FileFlag <FF>`) FilesOrPaths]
|           [-(:ref:`LC|Location <LC>`) StorageLocationFlags]
|           [-(:ref:`SR|Source <SR>`) ContributionSource]
|           [-(:ref:`DE|Description <DE>`) SavedFileDescriptions]
|           [-(:ref:`OF|OutputFile <OF>`) OutputFileName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.4.6:

  :ref:`Mode option <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - \-(:ref:`FO|FormatOutput <FO>`)
     - formats each column to a uniform fixed width

  Use -:ref:`FN <FN>` (-FieldNames) to specify which Help file fields to retrieve. Defaults
  to 'FINMTHSU'. Use -:ref:`FN <FN>` ALL for all available fields.

  Valid Help file field names and their corresponding :ref:`Info options <section5>`:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - F
     - \-(:ref:`HF|HelpFile <HF>`)
     - Help file names
   * - N
     - \-(:ref:`DF|DataFormat <DF>`)
     - file content formats
   * - M
     - \-(:ref:`AF|ArchiveFormat <AF>`)
     - file archive formats
   * - O
     - \-(:ref:`DO|DisplayOrder <DO>`)
     - display order indices
   * - T
     - \-(:ref:`HT|HelpFileType <HT>`)
     - Help file archiving types
   * - H
     - \-(:ref:`FS|FileStatus <FS>`)
     - Help file archiving status
   * - P
     - \-(:ref:`FF|FileFlag <FF>`)
     - File type flag, File or Path
   * - L
     - \-(:ref:`LC|Location <LC>`)
     - Help file storage location flag
   * - S
     - \-(:ref:`SZ|Size <SZ>`)
     - Help file sizes
   * - R
     - \-(:ref:`SR|Source <SR>`)
     - Help file contribution source
   * - I
     - \-(:ref:`ID|InitialDate <ID>`)
     - Date initially Published/Released
   * - J
     - \-(:ref:`FD|FileDate <FD>`)
     - date last modified on
   * - K
     - \-(:ref:`FT|FileTime <FT>`)
     - time last modified at
   * - U
     - \-(:ref:`WU|WebURL <WU>`)
     - a full URL for a remote help file
   * - D
     - \-(:ref:`DE|Description <DE>`)
     - file descriptions

  A dataset number is required unless Help file names are provided. If file
  names match multiple datasets and no dataset number is given, an error prompts
  the specialist to specify one and rerun.

  Results can be filtered by type (-:ref:`HT <HT>`) and description (-:ref:`DE <DE>`). Both -:ref:`HF <HF>` and
  -:ref:`DE <DE>` accept the '%' wildcard.




:ref:`Back to Top <index>`
