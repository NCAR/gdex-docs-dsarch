
.. _section3.1.1:

3.1.1 - Set Dataset Information
=====================


.. _SD:

Action Option -**SD** (-**SetDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

updates properties of an existing dataset record in
  GDEXDB — such as paths, file count limits, access flags, and data periods.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](SD|SetDataset) [`Mode Options <mode_>`_]
|         [-(`UD|UseDSARCH <section5.1_>`_) UseDSARCHFlag]
|         [-(`LC|Location <section5.2_>`_) AccessLocationFlag]
|         [-(`BF|BackupFlag <section5.2_>`_) QuasarBackupFlag]
|         [-(`DA|AccessFlag <section5.2_>`_) DataAccessFlags]
|         [-(`DF|DataFormat <section5.2_>`_) DataFormat]
|         [-(`WH|WebHome <section5.2_>`_) WebDataHomeDirectory]
|         [-(`WP|WebPath <section5.2_>`_) WebFilePath]
|         [-(`SP|SavedPath <section5.2_>`_) SavedFilePath]
|         [-(`FL|FileLimit <section5.1_>`_) FileCountLimit]
|         [-(`BL|ButtonLimit <section5.1_>`_) FileLimitShowButton]
|         [-(`GL|GroupLevel <section5.2_>`_) NumberOfGroupDisplay]
|         [-(`ML|MetaLink <section5.2_>`_) MetadataLink]
|         [-(`NW|NoteWeb <section5.2_>`_) WebNote]
|         [-(`ND|NoteDocument <section5.2_>`_) DocumentNote]
|         [-(`NS|NoteSoftware <section5.2_>`_) SoftwareNote]
|         [-(`NI|NoteInternal <section5.2_>`_) InternalNote]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]
|         [-(`KV|KeyValue <section5.2_>`_) KeyValuePairs]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|         [-(`BD|BeginDate <section5.2_>`_) BeginOnDates]
|         [-(`BT|BeginTime <section5.2_>`_) BeginAtTimes]
|         [-(`ED|EndDate <section5.2_>`_) EndOnDates]
|         [-(`ET|EndTime <section5.2_>`_) EndOnTimes]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`RT|ResetTGroup <section4_>`_)
     - resets the top group index for all Saved/Web file records
   * - -(`WM|WithMetadata <section4_>`_)
     - re-gathers Web file content metadata at dataset level
   * - -(`WN|WithFileNumber <section4_>`_)
     - re-evaluates and resets file counts

  Dataset numbers are normally created via the Metadata Manager (MM). Action
  -`SD`_ modifies the dataset record and any associated group data periods.
  Data periods for groups can be modified by **dsarch**, but must be created
  or removed through MM.

  The web file access location flag is set via -`LC <section5.2_>`_ (-Location). The default
  is 'G' (Glade Disk) when any web data files exist. The default becomes 'O'
  if all web files reside on Object Store, or 'C' if all are at the CGD data
  path.


.. _3.1.1_e1:

**EXAMPLE 1. To set the UseDSARCH flag, reset file counts and data size, and**

  set the beginning data date for dataset d744004:

=  ==========================================================================
   dsarch d744004 SD -`WN <section4_>`_ -UD Y -`BD <section5.2_>`_ 1999-07-01
=  ==========================================================================




:ref:`Back to Top <index>`
