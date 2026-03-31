
.. _section3.4.14:

3.4.14 - Move Saved/Web/Help/Quasar Files
=================================


.. _MV:

Action Option -**MV** (-**MoveFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

relocates archived files — across datasets, between groups,
or to a new name. One or more files may be moved per execution.

When a file's name or path changes, **dsarch** keeps the original name in GDEXDB
as a linked alias pointing to the new name.

Files can also be converted between types (Web to Saved or Saved to Web)
using :ref:`-TS <TS>` (-ToSaved) or :ref:`-TW <TW>` (-ToWeb).

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(MV|MoveFile) [:ref:`Mode Options <mode3.4.14>`]
|           [:ref:`-(OD|OriginDataset) <OD>` OriginalDataset]
|           [:ref:`-(RF|OriginFile) <RF>` OriginalSavedFileNames]
|            :ref:`-(SF|SavedFile) <SF>` SavedFileNames
|           [:ref:`-(OG|OriginGroup) <OG>` OriginalGroupIndices]
|           [:ref:`-(GI|GroupIndex) <GI>` NewGroupIndices]
|           [:ref:`-(OT|OriginType) <OT>` OriginalFileTypes]
|           [:ref:`-(ST|SavedFileType) <ST>` NewSavedFileTypes]
|           [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|           [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

or

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(MV|MoveFile) [:ref:`Mode Options <mode3.4.14>`]
|           [:ref:`-(OD|OriginDataset) <OD>` OriginalDataset]
|           [:ref:`-(RF|OriginFile) <RF>` OriginalWebFileNames]
|            :ref:`-(WF|WebFile) <WF>` WebFileNames
|           [:ref:`-(OG|OriginGroup) <OG>` OriginalGroupIndices]
|           [:ref:`-(GI|GroupIndex) <GI>` NewGroupIndices]
|           [:ref:`-(OT|OriginType) <OT>` OriginalFileTypes]
|           [:ref:`-(WT|WebFileType) <WT>` NewWebFileTypes]
|           [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|           [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

or

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(MV|MoveFile) [:ref:`Mode Options <mode3.4.14>`]
|           [:ref:`-(OD|OriginDataset) <OD>` OriginalDataset]
|           [:ref:`-(RF|OriginFile) <RF>` OriginalHelpFileNames]
|            :ref:`-(HF|HelpFile) <HF>` HelpFileNames
|           [:ref:`-(OT|OriginType) <OT>` OriginalFileTypes]
|           [:ref:`-(HT|HelpFileType) <HT>` NewHelpFileTypes]
|           [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|           [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

or

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(MV|MoveFile) [:ref:`Mode Options <mode3.4.14>`]
|           [:ref:`-(OD|OriginDataset) <OD>` OriginalDataset]
|           [:ref:`-(RF|OriginFile) <RF>` OriginalQuasarFileNames]
|            :ref:`-(QF|QuasarFile) <QF>` QuasarFileNames
|           [:ref:`-(OT|OriginType) <OT>` OriginalFileTypes]
|           [:ref:`-(QT|QuasarFileType) <QT>` NewQuasarFileTypes]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

or

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(MV|MoveFile) [:ref:`-TS <TS>`|:ref:`-TW <TW>`] [:ref:`Mode Options <mode3.4.14>`]
|           [:ref:`-(OD|OriginDataset) <OD>` OriginalDataset]
|           [:ref:`-(OG|OriginGroup) <OG>` OriginalGroupIndices]
|           [:ref:`-(WF|WebFile) <WF>` WebFileNames]
|           [:ref:`-(SF|SavedFile) <SF>` SavedFileNames]
|           [:ref:`-(GI|GroupIndex) <GI>` NewGroupIndices]
|           [:ref:`-(WT|WebFileType) <WT>` WebFileTypes]
|           [:ref:`-(ST|SavedFileType) <ST>` NewSavedFileTypes]
|           [:ref:`-(LC|Location) <LC>` StorageLocationFlags]
|           [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.14:

:ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(NE|NoEmail) <NE>`
     - suppresses email notification on failure
   * - :ref:`-(TS|ToSaved) <TS>`
     - moves Web files to Saved files
   * - :ref:`-(TW|ToWeb) <TW>`
     - moves Saved files to Web files
   * - :ref:`-(KM|KeepMetadata) <KM>`
     - used with :ref:`-TW <TW>` to retain the metadata record after the Web file is moved to a Saved file

Provide the file names to move via :ref:`-SF <SF>`, :ref:`-WF <WF>`, :ref:`-HF <HF>`, or :ref:`-QF <QF>`. Files are
physically moved only when the new path differs from the original. Dataset
links are updated to the new dataset number, and group indices are updated
if :ref:`-GI <GI>` (-GroupIndex) is specified.

If content metadata exists for the original Web file, it is automatically
transferred to the new file name via **rcm**.

If a DOI/Version-controlled Web file is renamed or converted to a Saved
file, its type is automatically set to 'V' (Version-controlled).



| :ref:`Back to Top <section3.4.14>`
| :ref:`Back to Table of Contents <index>`
