
.. _section3.4.14:

3.4.14 - Move Saved/Web/Help/Quasar Files
=====================


.. _MV:

Action Option -**MV** (-**MoveFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

relocates archived files — across datasets, between groups,
  or to a new name. One or more files may be moved per execution.

  When a file's name or path changes, **dsarch** keeps the original name in GDEXDB
  as a linked alias pointing to the new name.

  Files can also be converted between types (Web to Saved or Saved to Web)
  using -`TS <section4_>`_ (-ToSaved) or -`TW <section4_>`_ (-ToWeb).

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(MV|MoveFile) [`Mode Options <mode_>`_]
|         [-(`OD|OriginDataset <section5.2_>`_) OriginalDataset]
|         [-(`RF|OriginFile <section5.2_>`_) OriginalSavedFileNames]
|          -(`SF|SavedFile <section5.2_>`_) SavedFileNames
|         [-(`OG|OriginGroup <section5.2_>`_) OriginalGroupIndices]
|         [-(`GI|GroupIndex <section5.2_>`_) NewGroupIndices]
|         [-(`OT|OriginType <section5.2_>`_) OriginalFileTypes]
|         [-(`ST|SavedFileType <section5.2_>`_) NewSavedFileTypes]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(MV|MoveFile) [`Mode Options <mode_>`_]
|         [-(`OD|OriginDataset <section5.2_>`_) OriginalDataset]
|         [-(`RF|OriginFile <section5.2_>`_) OriginalWebFileNames]
|          -(`WF|WebFile <section5.2_>`_) WebFileNames
|         [-(`OG|OriginGroup <section5.2_>`_) OriginalGroupIndices]
|         [-(`GI|GroupIndex <section5.2_>`_) NewGroupIndices]
|         [-(`OT|OriginType <section5.2_>`_) OriginalFileTypes]
|         [-(`WT|WebFileType <section5.2_>`_) NewWebFileTypes]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(MV|MoveFile) [`Mode Options <mode_>`_]
|         [-(`OD|OriginDataset <section5.2_>`_) OriginalDataset]
|         [-(`RF|OriginFile <section5.2_>`_) OriginalHelpFileNames]
|          -(`HF|HelpFile <section5.2_>`_) HelpFileNames
|         [-(`OT|OriginType <section5.2_>`_) OriginalFileTypes]
|         [-(`HT|HelpFileType <section5.2_>`_) NewHelpFileTypes]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(MV|MoveFile) [`Mode Options <mode_>`_]
|         [-(`OD|OriginDataset <section5.2_>`_) OriginalDataset]
|         [-(`RF|OriginFile <section5.2_>`_) OriginalQuasarFileNames]
|          -(`QF|QuasarFile <section5.2_>`_) QuasarFileNames
|         [-(`OT|OriginType <section5.2_>`_) OriginalFileTypes]
|         [-(`QT|QuasarFileType <section5.2_>`_) NewQuasarFileTypes]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(MV|MoveFile) [-`TS <section4_>`_|-`TW <section4_>`_] [`Mode Options <mode_>`_]
|         [-(`OD|OriginDataset <section5.2_>`_) OriginalDataset]
|         [-(`OG|OriginGroup <section5.2_>`_) OriginalGroupIndices]
|         [-(`WF|WebFile <section5.2_>`_) WebFileNames]
|         [-(`SF|SavedFile <section5.2_>`_) SavedFileNames]
|         [-(`GI|GroupIndex <section5.2_>`_) NewGroupIndices]
|         [-(`WT|WebFileType <section5.2_>`_) WebFileTypes]
|         [-(`ST|SavedFileType <section5.2_>`_) NewSavedFileTypes]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`NE|NoEmail <section4_>`_)
     - suppresses email notification on failure
   * - -(`TS|ToSaved <section4_>`_)
     - moves Web files to Saved files
   * - -(`TW|ToWeb <section4_>`_)
     - moves Saved files to Web files
   * - -(`KM|KeepMetadata <section4_>`_)
     - used with -`TW <section4_>`_ to retain the metadata record after the Web file is moved to a Saved file

  Provide the file names to move via -`SF <section5.2_>`_, -`WF <section5.2_>`_, -`HF <section5.2_>`_, or -`QF <section5.2_>`_. Files are
  physically moved only when the new path differs from the original. Dataset
  links are updated to the new dataset number, and group indices are updated
  if -`GI <section5.2_>`_ (-GroupIndex) is specified.

  If content metadata exists for the original Web file, it is automatically
  transferred to the new file name via **rcm**.

  If a DOI/Version-controlled Web file is renamed or converted to a Saved
  file, its type is automatically set to 'V' (Version-controlled).




:ref:`Back to Top <index>`
