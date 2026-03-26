
.. _section3.4.7:

3.4.7 - Set Quasar File Information
=====================


.. _SQ:

Action Option -**SQ** (-**SetQuasarFile**) (Aliases: -**SetQuasar**, -**SetBackupFile**, -**SetBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

modifies information of the Quasar files
  in RDADB for a given dataset. One or multiple files can be processed each time.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](SS|SetSavedFile) [`Mode Options <#mode>`_]
|   [-(`QF|QuasarFile <section5.2.rst#QF>`_) QuasarFileNames]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`QT|QuasarFileType <section5.2.rst#QT>`_) QuasarFileTypes]
|   [-(`BS|BackupStatus <section5.2.rst#BS>`_) QuasarBackupFileStatus]
|   [-(`DF|DataFormat <section5.2.rst#DF>`_) FileContentFormat]
|   [-(`AF|ArchiveFormat <section5.2.rst#AF>`_) FileArchiveFormat]
|   [-(`DO <section5.2.rst#DO>`_|DisplayOrder] DisplayOrderIndices]
|   [-(`SZ|Size <section5.2.rst#SZ>`_) FileSizes]
|   [-(`MC|MD5Checksum <section5.2.rst#MC>`_) MD5ChecksumValues]
|   [-(`FD|FileDate <section5.2.rst#FD>`_) DateModified]
|   [-(`FT|FileTime <section5.2.rst#FT>`_) TimeModified]
|   [-(`DE <section5.2.rst#DE>`_|Description] SavedFileDescriptions]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`QS|QsubOptions <section5.1.rst#QS>`_)  PBSBatchOptions]
|   [-(`BP|BatchProcess <section5.2.rst#BP>`_) [BatchControlInfo]]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for setting Web file action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4.rst#BG>`_)
     - background process to turn off screen display for both standard outputs and errors
   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NE|NoEmail <section4.rst#NE>`_)
     - does not send email to the specialist for failed action
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`RO|ResetOrder <section4.rst#RO>`_)
     - resets the ordering indices of the list of file names on Quasar Server according to the order they are given per option -`QF <section5.2.rst#QF>`_. Reordering filelist can be also accomplished by giving option -`ON <section5.1.rst#ON>`_ (-OrderNames), which tells Action -`SQ <#SQ>`_ to reorder all the files of given dataset
   * - -(`SC|SetChecksum <section4.rst#SC>`_)
     - evaluates the md5 checksum values for data files on RDA Server and saves them into RDADB

  Quasar file names must be provided per option -`QF <section5.2.rst#QF>`_ (-QuasarFile) for this action
  to work, unless `Info Option <section5.rst>`_ -`ON <section5.1.rst#ON>`_ (-OrderNames) is provided to reorder the files
  of specified dataset. The number of values passed in following `Info <section5.rst>`_ options
  should match the number of file names given per option -`QF <section5.2.rst#QF>`_, except for options
  related to dataset information and the `Info <section5.rst>`_ options that are allowed to pass in
  as single values, such as -`AF <section5.2.rst#AF>`_ (-ArchiveFormat), -`DF <section5.2.rst#DF>`_ (-DataFormat), and -`QT <section5.2.rst#QT>`_
  (-QuasarFileType).



.. raw:: html

   <br>

:ref:`Back to Top <index>`
