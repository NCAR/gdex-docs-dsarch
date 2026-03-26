
.. _section3.1.1:

3.1.1 - Set Dataset Information
=====================


.. _SD:

Action Option -**SD** (-**SetDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

modifies dataset information into RDADB for a given
  dataset number.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](SD|SetDataset) [`Mode Options <#mode>`_]
|   [-(`UD|UseDSARCH <section5.1.rst#UD>`_) UseDSARCHFlag]
|   [-(`LC|Location <section5.2.rst#LC>`_) AccessLocationFlag]
|   [-(`BF|BackupFlag <section5.2.rst#BF>`_) QuasarBackupFlag]
|   [-(`DA|AccessFlag <section5.2.rst#DA>`_) DataAccessFlags]
|   [-(`DF|DataFormat <section5.2.rst#DF>`_) DataFormat]
|   [-(`WH|WebHome <section5.2.rst#WH>`_) WebDataHomeDirectory]
|   [-(`WP|WebPath <section5.2.rst#WP>`_) WebFilePath]
|   [-(`SP|SavedPath <section5.2.rst#SP>`_) SavedFilePath]
|   [-(`FL|FileLimit <section5.1.rst#FL>`_) FileCountLimit]
|   [-(`BL|ButtonLimit <section5.1.rst#BL>`_) FileLimitShowButton]
|   [-(`GL|GroupLevel <section5.2.rst#GL>`_) NumberOfGroupDisplay]
|   [-(`ML|MetaLink <section5.2.rst#ML>`_) MetadataLink]
|   [-(`NW|NoteWeb <section5.2.rst#NW>`_) WebNote]
|   [-(`ND|NoteDocument <section5.2.rst#ND>`_) DocumentNote]
|   [-(`NS|NoteSoftware <section5.2.rst#NS>`_) SoftwareNote]
|   [-(`NI|NoteInternal <section5.2.rst#NI>`_) InternalNote]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]
|   [-(`KV|KeyValue <section5.2.rst#KV>`_) KeyValuePairs]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`BD|BeginDate <section5.2.rst#BD>`_) BeginOnDates]
|   [-(`BT|BeginTime <section5.2.rst#BT>`_) BeginAtTimes]
|   [-(`ED|EndDate <section5.2.rst#ED>`_) EndOnDates]
|   [-(`ET|EndTime <section5.2.rst#ET>`_) EndOnTimes]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for setting dataset action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`RT|ResetTGroup <section4.rst#RT>`_)
     - reset top group index for all the Saved/Web file records
   * - -(`WM|WithMetadata <section4.rst#WM>`_)
     - re-gathers Web file content metadata at dataset level
   * - -(`WN|WithFileNumber <section4.rst#WN>`_)
     - reevaluates and resets file counts

  A given dataset number is normally added via dataset Metadata Manager (MM).
  The Action -`SD <#SD>`_ modifies dataset record, and the associated
  data periods for groups if any. Data periods for groups can be modified by
  **dsarch**, while they can be created, removed and modified per MM.

  The Web data accessing location flag of a dataset is provided via option
  -`LC <section5.2.rst#LC>`_ (-Location). The defualt value is 'G' for accessing web files from Glade
  Disk if there exists any web data files. A value of 'O' is set as default
  if all web data files of the dataset are on Object Store, and a value of 'C'
  is set as default if all web data files of the dataset are at CGD data path.


.. _e1:

**EXAMPLE 1. **

Set Dataset Information Of Use Dsarch Flag, Reset File Counts And
  data size, and beginning data date into RDADB for dataset number 'd744004'

  dsarch d744004 SD -`WN <section4.rst#WN>`_ -UD Y -`BD <section5.2.rst#BD>`_ 1999-07-01



.. raw:: html

   <br>

:ref:`Back to Top <index>`
