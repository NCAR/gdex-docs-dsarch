
.. _section3.4.3:

3.4.3 - Set Web File Information
=====================


.. _SW:

Action Option -**SW** (-**SetWebFile**) (Alias: -**SetWeb**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates and modifies information of files
  on RDA Server in RDADB for a given dataset. One or multiple files can be
  processed each time.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(SW|SetWebFile) [`Mode Options <#mode>`_]
|   [-(`WF|WebFile <section5.2.rst#WF>`_) webFileNames]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`GN|GroupName <section5.2.rst#GN>`_) GroupNames]
|   [-(`TG|TopGroupIndex <section5.2.rst#TG>`_) TopGroupIndices]
|   [-(`PO|PatternOffset <section5.1.rst#PO>`_) PatternStringOffset]
|   [-(`WT|WebFileType <section5.2.rst#WT>`_) WebFileTypes]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) WebFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`DF|DataFormat <section5.2.rst#DF>`_) DataFormats]
|   [-(`AF|ArchiveFormat <section5.2.rst#AF>`_) FileArchiveFormats]
|   [-(`DO <section5.2.rst#DO>`_|DisplayOrder] DisplayOrderIndices]
|   [-(`SZ|Size <section5.2.rst#SZ>`_) FileSizes]
|   [-(`MC|MD5Checksum <section5.2.rst#MC>`_) MD5ChecksumValues]
|   [-(`FD|FileDate <section5.2.rst#FD>`_) DateModified]
|   [-(`FT|FileTime <section5.2.rst#FT>`_) TimeModified]
|   [-(`ML|MetaLink <section5.2.rst#ML>`_) MetadataLinks]
|   [-(`TL|ThreddLink <section5.2.rst#TL>`_) ThreddCatalogLinks]
|   [-(`DE <section5.2.rst#DE>`_|Description] WebFileDescriptions]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`AL|AsyncLimit <section5.1.rst#AL>`_) AsyncProcessLimit]
|   [-(`QS|QsubOptions <section5.1.rst#QS>`_)  PBSBatchOptions]
|   [-(`BP|BatchProcess <section5.2.rst#BP>`_) [BatchControlInfo]]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for setting Web file action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4.rst#BG>`_)
     - background process to turn off screen display for both standard outputs and errors
   * - -(`DX|DeleteXML <section4.rst#DX>`_)
     - if present, calling **dcm** to delete file content metadata of specified Web files
   * - -(`EM|EMailNotice <section4.rst#EM>`_)
     - sends email for summary and errors for this action
   * - -(`GX|GatherXML <section4.rst#GX>`_)
     - evaluates file content metadata by calling **gatherxml**
   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NE|NoEmail <section4.rst#NE>`_)
     - does not send email to the specialist for failed action
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`RD|RemoveDir <section4.rst#RD>`_)
     - removes empty web directories
   * - -(`RO|ResetOrder <section4.rst#RO>`_)
     - resets the ordering indices of the list of file names on RDA Server according to the order they are given per option -`WF <section5.2.rst#WF>`_. Reordering filelist can be also accomplished by giving option -`ON <section5.1.rst#ON>`_ (-OrderNames), which tells Action -`SW <#SW>`_ to reorder all the files of given dataset and the involved groups
   * - -(`RS|GXRSOptions <section4.rst#RS>`_)
     - works with option -`GX <section4.rst#GX>`_ (-GatherXML) to speed up gatherxml
   * - -(`SC|SetChecksum <section4.rst#SC>`_)
     - evaluates the md5 checksum values for data files on RDA Server and saves them into RDADB

  Web file names must be provided per option -`WF <section5.2.rst#WF>`_ (-WebFile) for this action to
  work, unless `Info Option <section5.rst>`_ -`ON <section5.1.rst#ON>`_ (-OrderNames) is provided to reorder Web files
  of specified dataset and groups. The number of values passed in following
  `Info <section5.rst>`_ options should match the number of file names given per option -`WF <section5.2.rst#WF>`_,
  except for options related to dataset information and the `Info <section5.rst>`_ options that
  are allowed to pass in single values, such as -`GI <section5.2.rst#GI>`_ (-GroupIndex), -`AF <section5.2.rst#AF>`_
  (-ArchiveFormat), -`DF <section5.2.rst#DF>`_ (-DataFormat), and -`WT <section5.2.rst#WT>`_ (-WebFileType). If a single group
  index is provided for multiple Web file names, the index value is shared by
  all the given files on RDA Server.

  Pattern matching is used for identify a group index for a given Web file
  if group index is not given explicitly and `Info <section5.rst>`_ option -`PO <section5.1.rst#PO>`_ (-PatternOffset)
  if present. The Web file name is matched against group pattern values that
  are previously saved in group records via Action -`SG <section3.3.1.rst>`_ (-SetGroup).

  The web file status can be set to either P (public) or I (internal) for data
  type D (data), N (ncar data), O (document) and S (software). For a Web file is
  set to be under an Internal group, its status is automatically forced to I.

  If a Web file is set to be under an Internal group, its status is forced to I.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
