
.. _section3.4.1:

3.4.1 - Set Saved File Information
=====================


.. _SS:

Action Option -**SS** (-**SetSavedFile**) (Alias: -**SetSaved**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates and modifies information of
  the Saved files in RDADB for a given dataset. One or multiple files can be
  processed each time.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](SS|SetSavedFile) [`Mode Options <#mode>`_]
|   [-(`SF|SavedFile <section5.2.rst#SF>`_) SavedFileNames]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`GN|GroupName <section5.2.rst#GN>`_) GroupNames]
|   [-(`TG|TopGroupIndex <section5.2.rst#TG>`_) TopGroupIndices]
|   [-(`PO|PatternOffset <section5.1.rst#PO>`_) PatternStringOffset]
|   [-(`ST|SavedFileType <section5.2.rst#ST>`_) SavedFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) SavedFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`DF|DataFormat <section5.2.rst#DF>`_) DataFormats]
|   [-(`AF|ArchiveFormat <section5.2.rst#AF>`_) FileArchiveFormats]
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
   * - -(`EM|EMailNotice <section4.rst#EM>`_)
     - sends email for summary and errors for this action
   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NE|NoEmail <section4.rst#NE>`_)
     - does not send email to the specialist for failed action
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`RD|RemoveDir <section4.rst#RD>`_)
     - removes empty web directories
   * - -(`RO|ResetOrder <section4.rst#RO>`_)
     - resets the ordering indices of the list of file names on Saved Server according to the order they are given per option -`SF <section5.2.rst#SF>`_. Reordering filelist can be also accomplished by giving option -`ON <section5.1.rst#ON>`_ (-OrderNames), which tells Action -`SW <section3.4.3.rst>`_ to reorder all the files of given dataset and the involved groups
   * - -(`SC|SetChecksum <section4.rst#SC>`_)
     - evaluates the md5 checksum values for data files on RDA Server and saves them into RDADB

  Saved file names must be provided per option -`SF <section5.2.rst#SF>`_ (-SavedFile) for this action to
  work, unless `Info Option <section5.rst>`_ -`ON <section5.1.rst#ON>`_ (-OrderNames) is provided to reorder Saved files
  of specified dataset and groups. The number of values passed in following
  `Info <section5.rst>`_ options should match the number of file names given per option -`SF <section5.2.rst#SF>`_,
  except for options related to dataset information and the `Info <section5.rst>`_ options that
  are allowed to pass in single values, such as -`GI <section5.2.rst#GI>`_ (-GroupIndex), -`AF <section5.2.rst#AF>`_
  (-ArchiveFormat), -`DF <section5.2.rst#DF>`_ (-DataFormat), and -`ST <section5.2.rst#ST>`_ (-SavedFileType). If a single group
  index is provided for multiple Saved file names, the index value is shared by
  all the given files on RDA Server.

  Pattern matching is used for identify a group index for a given saved file
  if group index is not given explicitly and `Info <section5.rst>`_ option -`PO <section5.1.rst#PO>`_ (-PatternOffset)
  if present. The Web file name is matched against group pattern values that
  are previously saved in group records via Action -`SG <section3.3.1.rst>`_ (-SetGroup).



.. raw:: html

   <br>

:ref:`Back to Top <index>`
