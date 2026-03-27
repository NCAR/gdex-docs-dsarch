
.. _section3.4.15:

3.4.15 - Delete Saved/Web/Help/Quasar Files
=====================


.. _DL:

Action Option -**DL** (-**Delete**) (Aliases: -**RM**, -**Remove**, -**DeleteFile**, -**RemoveFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

permanently
  removes files from GDEX Servers and deletes their records from GDEXDB.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(DL|Delete) [`Mode Options <mode_>`_]
|         [-(`SF|SavedFile <section5.2_>`_) SavedFileNames]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|          -(`ST|SavedFileType <section5.2_>`_) SavedFileTypes
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(DL|Delete) [`Mode Options <mode_>`_]
|         [-(`WF|WebFile <section5.2_>`_) WebFileNames]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|          -(`WT|WebFileType <section5.2_>`_) WebFileTypes
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(DL|Delete) [`Mode Options <mode_>`_]
|         [-(`HF|HelpFile <section5.2_>`_) HelpFileNames]
|          -(`HT|HelpFileType <section5.2_>`_) HelpFileTypes
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(DL|Delete) [`Mode Options <mode_>`_]
|         [-(`QF|QuasarFile <section5.2_>`_) QuasarFileNames]
|          -(`QT|QuasarFileType <section5.2_>`_) QuasarFileTypes
|         [-(`DD|DeleteDir <section5.1_>`_) DeleteDirLevel]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`DX|DeleteXML <section4_>`_)
     - calls **dcm** to delete content metadata for the Web files being deleted
   * - -(`EM|EMailNotice <section4_>`_)
     - sends an email summary (including any errors) when the action completes or aborts
   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NE|NoEmail <section4_>`_)
     - suppresses email notification on failure
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`RD|RemoveDir <section4_>`_)
     - removes empty Saved or Web directories after deletion

  Provide the file names to delete via -`SF <section5.2_>`_, -`WF <section5.2_>`_, -`HF <section5.2_>`_, or -`QF <section5.2_>`_. Use -`DD <section5.1_>`_
  (-DeleteDir) to specify how many levels of empty parent directories to
  remove after deletion.




:ref:`Back to Top <index>`
