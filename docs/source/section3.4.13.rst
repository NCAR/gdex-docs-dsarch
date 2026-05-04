
.. _section3.4.13:

3.4.13 - Restore Quasar Files
=================================


.. _RQ:

Action Option -**RQ** (-**RestoreQuasarFile**) (Aliases: -**RestoreQuasar**, -**RestoreBackupFile**, -**RestoreBackup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -RestoreQuasar|-RestoreBackupFile|-RestoreBackup),
finds the Quasar tar files containing the specified Saved and/or Web
files, downloads them from the Globus Quasar Server, and restores
any files missing from the GDEX Server.

| **dsarch** [:ref:`-(DS|dataset) <DS>`] dNNNNNN -(RQ|RestoreQuasarFile) [:ref:`Mode Options <mode3.4.13>`]
|           [:ref:`-(QF|QuasarFile) <QF>` QuasarFileNames]
|           [:ref:`-(SF|SavedFile) <SF>` SavedFileNames]
|           [:ref:`-(ST|SavedFileType) <ST>` SavedFileTypes]
|           [:ref:`-(WF|WebFile) <WF>` webFileNames]
|           [:ref:`-(WT|WebFileType) <WT>` WebFileTypes]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
|           [:ref:`-(BP|BatchProcess) <BP>` [BatchControlInfo]]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(BG|BackGround) <BG>`
     - runs in background; suppresses screen output and errors
   * - :ref:`-(EM|EMailNotice) <EM>`
     - sends an email summary (including any errors) when the action completes or aborts
   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NE|NoEmail) <NE>`
     - suppresses email notification on failure
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing

At least one Quasar, Saved, and/or Web file name must be provided via
:ref:`-QF <QF>`, :ref:`-SF <SF>`, and/or :ref:`-WF <WF>`. If only Quasar file names are given, the tar
files are retrieved from the server but no Saved or Web files are
restored.



| :ref:`Back to Top <section3.4.13>`
| :ref:`Back to Table of Contents <index>`
