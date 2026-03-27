
.. _section3.1.1:

3.1.1 - Set Dataset Information
=====================


.. _SD:

Action Option -**SD** (-**SetDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

updates properties of an existing dataset record in
  GDEXDB — such as paths, file count limits, access flags, and data periods.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN [-](SD|SetDataset) [:ref:`Mode Options <mode3.1.1>`]
|         [-(:ref:`UD|UseDSARCH <UD>`) UseDSARCHFlag]
|         [-(:ref:`LC|Location <LC>`) AccessLocationFlag]
|         [-(:ref:`BF|BackupFlag <BF>`) QuasarBackupFlag]
|         [-(:ref:`DA|AccessFlag <DA>`) DataAccessFlags]
|         [-(:ref:`DF|DataFormat <DF>`) DataFormat]
|         [-(:ref:`WH|WebHome <WH>`) WebDataHomeDirectory]
|         [-(:ref:`WP|WebPath <WP>`) WebFilePath]
|         [-(:ref:`SP|SavedPath <SP>`) SavedFilePath]
|         [-(:ref:`FL|FileLimit <FL>`) FileCountLimit]
|         [-(:ref:`BL|ButtonLimit <BL>`) FileLimitShowButton]
|         [-(:ref:`GL|GroupLevel <GL>`) NumberOfGroupDisplay]
|         [-(:ref:`ML|MetaLink <ML>`) MetadataLink]
|         [-(:ref:`NW|NoteWeb <NW>`) WebNote]
|         [-(:ref:`ND|NoteDocument <ND>`) DocumentNote]
|         [-(:ref:`NS|NoteSoftware <NS>`) SoftwareNote]
|         [-(:ref:`NI|NoteInternal <NI>`) InternalNote]
|         [-(:ref:`DB|Debug <DB>`) DebugModeInfo]
|         [-(:ref:`KV|KeyValue <KV>`) KeyValuePairs]
|         [-(:ref:`GI|GroupIndex <GI>`) GroupIndices]
|         [-(:ref:`BD|BeginDate <BD>`) BeginOnDates]
|         [-(:ref:`BT|BeginTime <BT>`) BeginAtTimes]
|         [-(:ref:`ED|EndDate <ED>`) EndOnDates]
|         [-(:ref:`ET|EndTime <ET>`) EndOnTimes]

.. _mode3.1.1:

  :ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(:ref:`MD|MyDataset <MD>`)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(:ref:`NT|NoTrim <NT>`)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(:ref:`RT|ResetTGroup <RT>`)
     - resets the top group index for all Saved/Web file records
   * - -(:ref:`WM|WithMetadata <WM>`)
     - re-gathers Web file content metadata at dataset level
   * - -(:ref:`WN|WithFileNumber <WN>`)
     - re-evaluates and resets file counts

  Dataset numbers are normally created via the Metadata Manager (MM). Action
  -:ref:`SD <SD>` modifies the dataset record and any associated group data periods.
  Data periods for groups can be modified by **dsarch**, but must be created
  or removed through MM.

  The web file access location flag is set via -:ref:`LC <LC>` (-Location). The default
  is 'G' (Glade Disk) when any web data files exist. The default becomes 'O'
  if all web files reside on Object Store, or 'C' if all are at the CGD data
  path.


.. _3.1.1_e1:

**EXAMPLE 1. To set the UseDSARCH flag, reset file counts and data size, and**

  set the beginning data date for dataset d744004:

=  ==================================================================
   dsarch d744004 SD -:ref:`WN <WN>` -UD Y -:ref:`BD <BD>` 1999-07-01
=  ==================================================================




:ref:`Back to Top <index>`
