
.. _section3.4.10:

3.4.10 - Archive Web Files
=====================


.. _AW:

Action Option -**AW** (-**ArchiveWebFile**) (Aliases: -**ArchiveWeb**, -**ArchWeb**, -**ArchWebFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

archives
  local data files onto RDA Server and saves information of the archived files
  into RDADB for a given dataset. One or multiple local files can be archived
  each time.

| **dsarch** [-(`DS|dataset <section5.1.rst#DS>`_)] dsnnn.n -(AW|ArchiveWebFile) [`Mode Options <#mode>`_]
|   [-(`LF|LocalFile <section5.2.rst#LF>`_) LocalFileNames]
|   [-(`LD|LocalDirectory <section5.1.rst#LD>`_) LocalDirectoryName]
|   [-(`LL|LocalFileList <section5.1.rst#LL>`_) LocalFileListName]
|   [-(`WF|WebFile <section5.2.rst#WF>`_) webFileNames]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`TG|TopGroupIndex <section5.2.rst#TG>`_) TopGroupIndices]
|   [-(`GN|GroupName <section5.2.rst#GN>`_) GroupNames]
|   [-(`PO|PatternOffset <section5.1.rst#PO>`_) PatternStringOffset]
|   [-(`WT|WebFileType <section5.2.rst#WT>`_) WebFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) WebFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`DF|DataFormat <section5.2.rst#DF>`_) DataFormat]
|   [-(`AF|ArchiveFormat <section5.2.rst#AF>`_) FileArchiveFormat]
|   [-(`DO <section5.2.rst#DO>`_|DisplayOrder] DisplayOrderIndices]
|   [-(`SZ|Size <section5.2.rst#SZ>`_) FileSizes]
|   [-(`MC|MD5Checksum <section5.2.rst#MC>`_) MD5ChecksumValues]
|   [-(`DE <section5.2.rst#DE>`_|Description] WebFileDescriptions]
|   [-(`VS|ValidSize <section5.1.rst#VS>`_) MinSizeForValidFile]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`AL|AsyncLimit <section5.1.rst#AL>`_) AsyncProcessLimit]
|   [-(`QS|QsubOptions <section5.1.rst#QS>`_)  PBSBatchOptions]
|   [-(`BP|BatchProcess <section5.2.rst#BP>`_) [BatchControlInfo]]
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteLocalDirLevel]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for archive web file action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4.rst#BG>`_)
     - background process to turn off screen display for both standard outputs and errors
   * - -(`CL|CleanLocal <section4.rst#CL>`_)
     - cleans local files after they are all archived onto RDA Server successfully
   * - -(`EM|EMailNotice <section4.rst#EM>`_)
     - sends email for summary and errors for this action
   * - -(`GX|GatherXML <section4.rst#GX>`_)
     - evaluates file content metadata from local file directly by calling **gatherxml**
   * - -(`GZ|GMTZone <section4.rst#GZ>`_)
     - uses GMT dates/times as controlling times
   * - -(`KP|KeepLocalPath <section4.rst#KP>`_)
     - retains the path names of local files as relative paths to data home directory on RDA Server
   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NE|NoEmail <section4.rst#NE>`_)
     - does not send email to the specialist for failed action
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`OE|OverrideExist <section4.rst#OE>`_)
     - overrides existing web files
   * - -(`RO|ResetOrder <section4.rst#RO>`_)
     - resets the ordering indices of the list of file names on RDA Server according to the order they are given per option -`SF <section5.2.rst#SF>`_. Reordering filelist can be also accomplished by giving option -`ON <section5.1.rst#ON>`_ (-OrderNames), which tells Action -`SS <section3.4.1.rst>`_ to reorder all the files of given dataset and the involved groups
   * - -(`SC|SetChecksum <section4.rst#SC>`_)
     - evaluates the md5 checksum values for data files on Saved Server and saves them into RDADB
   * - -(`UZ|UpzipData <section4.rst#UZ>`_)
     - uncompresses online data with one of the uncompressing utilities,  'gunzip', 'uncompress', 'unzip' or 'bunzip', according to the file name extensions of ".gz', '.Z', '.zip' or '.bz2', respectively
   * - -(`XC|CrossCopy <section4.rst#XC>`_)
     - copies files from existing web/Object data files to missing Object/Web files; information of the Web files saved in RDADB is used for missing data copies
   * - -(`XM|CrossMove <section4.rst#XM>`_)
     - moves files from existing web/Object data files to missing Object/Web files; information of the Web files saved in RDADB is used for missing data copies
   * - -(`ZD|ZipData <section4.rst#ZD>`_)
     - compresses online data with one of the compressing utilities,  'gzip', 'compress', 'zip' or 'bzip', according to the archiving format 'GZ', 'Z', 'ZIP' or 'BZ2' provided per option -`AF <section5.2.rst#AF>`_ (-ARchiveFormat), respectively

  One or multiple local file names can be provided per option -`LF <section5.2.rst#LF>`_ (-LocalFile)
  for this action to work. If option -`LF <section5.2.rst#LF>`_ is given on command line, '*' and '?'
  can be used in local file names for wildcard match. File names must include
  relative or absolute paths if local data files are not located in the
  directory where **dsarch** is started. The local file names are gathered
  recursively following the sub-directory tree if a local directory per `Info <section5.rst>`_
  option -`LD <section5.1.rst#LD>`_ (-LocalDirectory) is present.

  Local file names are used as default for Web file names unless they are
  explicitly given per option -`WF <section5.2.rst#WF>`_ (-WebFile). Local files are archived onto
  RDA Server under the dataset home directory as default, unless relative or
  absolute paths are given per option -`WP <section5.2.rst#WP>`_ (-WebPath) or Web path information for
  the given dataset, and groups if specified, previously saved in RDADB. The
  original local file names, including paths, are used if `Mode <section4.rst>`_ option -`KP <section4.rst#KP>`_
  (-KeepLocalPath) is specified. Option -`WP <section5.2.rst#WP>`_ is not allowed if `Mode <section4.rst>`_ option -`KP <section4.rst#KP>`_
  is given.

  Group information for data files to be archived are given per option -`GI <section5.2.rst#GI>`_
  (-GroupIndex) or -`GN <section5.2.rst#GN>`_ (-GroupName). Pattern matching is used for identify a
  group index for a given Web file if group index is not given explicitly, and
  the file record not exists in RDADB yet or `Info <section5.rst>`_ option -`PO <section5.1.rst#PO>`_ (-PatternOffset)
  if present. The Web or local file name is matched against group pattern values
  that are previously saved in group records via Action -`SG <section3.3.1.rst>`_ (-SetGroup). If no
  group index is provided and no group pattern matching, an index value of 0
  is defaulted for a data file to indicate no group.

  A web file can be archived as either P (public) or I (internal) for any data type
  as D (data) or N (ncar data). For a Web file is archived to be under an Internal
  group, its status is automatically forced to I.

  The number of values passed in per `Info <section5.rst>`_ options must be the same as the number
  of local file names provided, except for the `Info <section5.rst>`_ options that are allowed to
  pass in single values, such as options -`GI <section5.2.rst#GI>`_ (-GroupIndex), -`DF <section5.2.rst#DF>`_ (-DataFormat),
  -`AF <section5.2.rst#AF>`_ (-ArchiveFormat), -`WT <section5.2.rst#WT>`_ (-WebFileType), and -`WP <section5.2.rst#WP>`_ (-WebPath). If a single
  group index is provided for multiple given local file names, the group index
  is shared by all the given data files.

  The location flag is provided via option -`LC <section5.2.rst#LC>`_ (-Location). The defualt value
  is 'G' for archiving a web file onto Glade Disk only.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
