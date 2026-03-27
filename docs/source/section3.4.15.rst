
.. _section3.4.15:

3.4.15 - Delete Saved/Web/Help/Quasar Files
=====================


.. _DL:

Action Option -**DL** (-**Delete**) (Aliases: -**RM**, -**Remove**, -**DeleteFile**, -**RemoveFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

deletes data
  files on RDA Servers and their RDADB records.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(DL|Delete) [`Mode Options <#mode>`_]
|   [-(`SF|SavedFile <section5.2.rst#SF>`_) SavedFileNames]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   -(`ST|SavedFileType <section5.2.rst#ST>`_) SavedFileTypes
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(DL|Delete) [`Mode Options <#mode>`_]
|   [-(`WF|WebFile <section5.2.rst#WF>`_) WebFileNames]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   -(`WT|WebFileType <section5.2.rst#WT>`_) WebFileTypes
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(DL|Delete) [`Mode Options <#mode>`_]
|   [-(`HF|HelpFile <section5.2.rst#HF>`_) HelpFileNames]
|   -(`HT|HelpFileType <section5.2.rst#HT>`_) HelpFileTypes
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

      or

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(DL|Delete) [`Mode Options <#mode>`_]
|   [-(`QF|QuasarFile <section5.2.rst#QF>`_) QuasarFileNames]
|   -(`HT|HelpFileType <section5.2.rst#HT>`_) HelpFileTypes
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteDirLevel]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for deleting file action:

.. list-table::
   :widths: auto

   * - -(`DX|DeleteXML <section4.rst#DX>`_)
     - if present, calling **dcm** to delete file content metadata of the Web files to be deleted
   * - -(`EM|EMailNotice <section4.rst#EM>`_)
     - sends email for summary and errors for this action
   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NE|NoEmail <section4.rst#NE>`_)
     - does not send email to the specialist for failed action
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`RD|RemoveDir <section4.rst#RD>`_)
     - removes empty saved or web directories

  Use this action to delete data files on RDA Server. The Saved, Web, Help or Quasar
  File names are provided per option -`SF <section5.2.rst#SF>`_ (-SavedFile), -`WF <section5.2.rst#WF>`_ (-WebFile), -`HF <section5.2.rst#HF>`_ (-HelpFile),
  or -`QF <section5.2.rst#QF>`_ (-Quasarfile), respectively.

  Specify the number of levels of directories via `Info <section5.rst>`_ option -`DD <section5.1.rst#DD>`_ (-DeleteDir)
  for the directories to be deleted if Saved or Web files inside them are all
  deleted.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
