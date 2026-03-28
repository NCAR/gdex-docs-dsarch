
.. _section3.4.15:

3.4.15 - Delete Saved/Web/Help/Quasar Files
=====================


.. _DL:

Action Option -**DL** (-**Delete**) (Aliases: -**RM**, -**Remove**, -**DeleteFile**, -**RemoveFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

permanently
removes files from GDEX Servers and deletes their records from GDEXDB.

|  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(DL|Delete) [:ref:`Mode Options <mode3.4.15>`]
|             [:ref:`-(SF|SavedFile) <SF>` SavedFileNames]
|             [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|              :ref:`-(ST|SavedFileType) <ST>` SavedFileTypes
|             [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|             [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

or

|  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(DL|Delete) [:ref:`Mode Options <mode3.4.15>`]
|             [:ref:`-(WF|WebFile) <WF>` WebFileNames]
|             [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|              :ref:`-(WT|WebFileType) <WT>` WebFileTypes
|             [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|             [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

or

|  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(DL|Delete) [:ref:`Mode Options <mode3.4.15>`]
|             [:ref:`-(HF|HelpFile) <HF>` HelpFileNames]
|              :ref:`-(HT|HelpFileType) <HT>` HelpFileTypes
|             [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|             [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

or

|  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN -(DL|Delete) [:ref:`Mode Options <mode3.4.15>`]
|             [:ref:`-(QF|QuasarFile) <QF>` QuasarFileNames]
|              :ref:`-(QT|QuasarFileType) <QT>` QuasarFileTypes
|             [:ref:`-(DD|DeleteDir) <DD>` DeleteDirLevel]
|             [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.15:

:ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(DX|DeleteXML) <DX>`
     - calls **dcm** to delete content metadata for the Web files being deleted
   * - :ref:`-(EM|EMailNotice) <EM>`
     - sends an email summary (including any errors) when the action completes or aborts
   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NE|NoEmail) <NE>`
     - suppresses email notification on failure
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(RD|RemoveDir) <RD>`
     - removes empty Saved or Web directories after deletion

Provide the file names to delete via :ref:`-SF <SF>`, :ref:`-WF <WF>`, :ref:`-HF <HF>`, or :ref:`-QF <QF>`. Use :ref:`-DD <DD>`
(-DeleteDir) to specify how many levels of empty parent directories to
remove after deletion.




:ref:`Back to Top <index>`
