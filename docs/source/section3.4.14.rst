
.. _section3.4.14:

3.4.14 - Move Saved/Web/Help/Quasar Files
=====================


.. _MV:

Action Option -**MV** (-**MoveFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

moves files archived on RDA Server from an original dataset
  per option -`OD <section5.2.rst#OD>`_ (-OriginDataset) to a different dataset per option -`DS <section5.1.rst#DS>`_ (-Dataset),
  or from one group to another in the same dataset, or just simply to different
  file names. One or multiple files can be moved each time.

  If, after moved, a file name, including path, is different from its original name,
  the original name is recorded in RDADB with link to the new data file name.

  Files can be moved cross servers between Web and Saved files if `Mode <section4.rst>`_ options -`TS <section4.rst#TS>`_
  (-ToSaved) or -`TW <section4.rst#TW>`_ (-ToWeb).

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(MV|MoveFile) [`Mode Options <#mode>`_]
|   [-(`OD|OriginDataset <section5.2.rst#OD>`_) OriginalDataset]
|   [-(`RF|OriginFile <section5.2.rst#RF>`_) OriginalSavedFileNames]
|   -(`SF|SavedFile <section5.2.rst#SF>`_) SavedFileNames
|   [-(`OG|OriginGroup <section5.2.rst#OG>`_) OriginalGroupIndices]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) NewGroupIndices]
|   [-(`OT|OriginType <section5.2.rst#OT>`_) OriginalFileTypes]
|   [-(`ST|SavedFileType <section5.2.rst#ST>`_) NewSavedFileTypes]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(MV|MoveFile) [`Mode Options <#mode>`_]
|   [-(`OD|OriginDataset <section5.2.rst#OD>`_) OriginalDataset]
|   [-(`RF|OriginFile <section5.2.rst#RF>`_) OriginalWebFileNames]
|   -(`WF|WebFile <section5.2.rst#WF>`_) WebFileNames
|   [-(`OG|OriginGroup <section5.2.rst#OG>`_) OriginalGroupIndices]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) NewGroupIndices]
|   [-(`OT|OriginType <section5.2.rst#OT>`_) OriginalFileTypes]
|   [-(`WT|WebFileType <section5.2.rst#WT>`_) NewWebFileTypes]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(MV|MoveFile) [`Mode Options <#mode>`_]
|   [-(`OD|OriginDataset <section5.2.rst#OD>`_) OriginalDataset]
|   [-(`RF|OriginFile <section5.2.rst#RF>`_) OriginalHelpFileNames]
|   -(`HF|HelpFile <section5.2.rst#HF>`_) HelpFileNames
|   [-(`OT|OriginType <section5.2.rst#OT>`_) OriginalFileTypes]
|   [-(`HT|HelpFileType <section5.2.rst#HT>`_) NewHelpFileTypes]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(MV|MoveFile) [`Mode Options <#mode>`_]
|   [-(`OD|OriginDataset <section5.2.rst#OD>`_) OriginalDataset]
|   [-(`RF|OriginFile <section5.2.rst#RF>`_) OriginalQuasarFileNames]
|   -(`QF|QuasarFile <section5.2.rst#QF>`_) QuasarFileNames
|   [-(`OT|OriginType <section5.2.rst#OT>`_) OriginalFileTypes]
|   [-(`QT|QuasarFileType <section5.2.rst#QT>`_) NewQuasarFileTypes]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(MV|MoveFile) [-`TS <section4.rst#TS>`_|-`TW <section4.rst#TW>`_] [`Mode Options <#mode>`_]
|   [-(`OD|OriginDataset <section5.2.rst#OD>`_) OriginalDataset]
|   [-(`OG|OriginGroup <section5.2.rst#OG>`_) OriginalGroupIndices]
|   [-(`WF|WebFile <section5.2.rst#WF>`_) WebFileNames]
|   [-(`SF|SavedFile <section5.2.rst#SF>`_) SavedFileNames]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) NewGroupIndices]
|   [-(`WT|WebFileType <section5.2.rst#WT>`_) WebFileTypes]
|   [-(`ST|SavedFileType <section5.2.rst#ST>`_) NewSavedFileTypes]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skips trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`NE|NoEmail <section4.rst#NE>`_)
     - does not send email to the specialist for failed action
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`TS|ToSaved <section4.rst#TS>`_)
     - move Web Files to Saved files
   * - -(`TW|ToWeb <section4.rst#TW>`_)
     - move Saved Files to Web files
   * - -(`KM|KeepMetadata <section4.rst#KM>`_)
     - works with option -`TW <section4.rst#TW>`_ to keep the metadata record for later use after the web file record is moved to savefile

  Use this action to move Saved/Web/Help/Quasar files, Saved File names, Web File Names,
  Help file names, or Quasar backup file names are provided per option, -`SF <section5.2.rst#SF>`_ (-SavedFile),
  -`WF <section5.2.rst#WF>`_ (-WebFile), -`HF <section5.2.rst#HF>`_ (-HelpFile), or -`QF <section5.2.rst#QF>`_ (-QuasarFile), respectively. It is allowed to
  move Web to Saved files, or Saved to Web files. A data file is only physically moved
  if its new and original paths are different. Dataset links for the data files are
  pointed to the new dataset number. For Saved and Web files, group indices are changed
  to new ones if specified per option -`GI <section5.2.rst#GI>`_ (-GroupIndex).

  If content metadata is gathered for the original Web file, the metadata information
  is automatically transfered to the new file by cammnd **rcm**.

  If a Web file of a dataset under DOI/Version control is moved to a different name,
  or to a Saved file, its data type is automatically changed to 'V 'as Version
  controlled type.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
