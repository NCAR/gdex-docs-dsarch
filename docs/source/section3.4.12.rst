
.. _section3.4.12:

3.4.12 - Backup Quasar Files
=====================


.. _AQ:

Action Option -**AQ** (-**ArchiveQuasarFile**) (Aliases: -**ArchiveQuasar**, -**ArchiveBackupFile**, -**ArchiveBackup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

(Alias: -ArchiveQuasar|-ArchiveBackupFile|-ArchiveBackup),
packages archived Saved and/or Web files into a single tar file and uploads it
to the Globus Quasar Server for long-term backup, recording the result in
GDEXDB. In practice, the companion utility 'dsquasar' handles identifying
files to back up, building optimally sized input lists (1-3 GB each), and
calling this action. See 'dsquasar' help for details.

.. code-block:: bash

  **dsarch** [:ref:`-(DS|dataset) <DS>`] dNNNNNN -(AQ|ArchiveQuasarFile) [:ref:`Mode Options <mode3.4.12>`]
         [:ref:`-(SF|SavedFile) <SF>` SavedFileNames]
         [:ref:`-(ST|SavedFileType) <ST>` SavedFileTypes]
         [:ref:`-(WF|WebFile) <WF>` webFileNames]
         [:ref:`-(WT|WebFileType) <WT>` WebFileTypes]
         [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
         [:ref:`-(QS|QsubOptions) <QS>`  PBSBatchOptions]
         [:ref:`-(BP|BatchProcess) <BP>` [BatchControlInfo]]
         [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.4.12:

:ref:`Mode options <section4>` that can be specified for this action:

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
   * - :ref:`-(OE|OverrideExist) <OE>`
     - overwrites existing Quasar files
   * - :ref:`-(TO|TarOnly) <TO>`
     - creates the tar file only, without uploading it to the Globus Quasar Server
   * - :ref:`-(XC|CrossCopy) <XC>`
     - copies files from existing Quasar Backup and Disaster Recovery files to fill missing Backup/Drdata copies, using GDEXDB records for guidance

At least one Saved and/or Web file name must be provided via -:ref:`SF <SF>` and/or -:ref:`WF <WF>`.




:ref:`Back to Top <index>`
