
.. _section3.4.11:

3.4.11 - Archive Help Files
=====================


.. _AH:

Action Option -**AH** (-**ArchiveHelpFile**) (Aliases: -**ArchiveHelp**, -**ArchHelp**, -**ArchHelpFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 (Alias: -ArchiveHelp|-ArchHelp|-ArchHelpFile),
  archives local files as files and saved information of the archived files
  into RDADB for a given dataset. One or multiple local files can be archived
  each time.

| **dsarch** [-(`DS|dataset <section5.1.rst#DS>`_)] dsnnn.n -(AH|ArchiveHelpFile) [`Mode Options <#mode>`_]
|   -(`LF|LocalFile <section5.2.rst#LF>`_) LocalFileNames
|   [-(`HF|HelpFile <section5.2.rst#HF>`_) HelpFileNames]
|   [-(`HT|HelpFileType <section5.2.rst#HT>`_) HelpFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) HelpFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`DF|DataFormat <section5.2.rst#DF>`_) FileContentFormat]
|   [-(`AF|ArchiveFormat <section5.2.rst#AF>`_) FileArchiveFormat]
|   [-(`DO <section5.2.rst#DO>`_|DisplayOrder] DisplayOrderIndices]
|   [-(`SZ|Size <section5.2.rst#SZ>`_) FileSizes]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`MC|MD5Checksum <section5.2.rst#MC>`_) MD5ChecksumValues]
|   [-(`DE <section5.2.rst#DE>`_|Description] SavedFileDescriptions]
|   [-(`VS|ValidSize <section5.1.rst#VS>`_) MinSizeForValidFile]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`QS|QsubOptions <section5.1.rst#QS>`_)  PBSBatchOptions]
|   [-(`BP|BatchProcess <section5.2.rst#BP>`_) [BatchControlInfo]]
|   [-(`DD|DeleteDir <section5.1.rst#DD>`_) DeleteLocalDirLevel]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for archive help file action:

.. list-table::
   :widths: auto

   * - -(`BG|BackGround <section4.rst#BG>`_)
     - background process to turn off screen display for both standard outputs and errors
   * - -(`CL|CleanLocal <section4.rst#CL>`_)
     - cleans local files after they are all archived onto RDA Web Server successfully
   * - -(`EM|EMailNotice <section4.rst#EM>`_)
     - sends email for summary and errors for this action
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
     - resets the ordering indices of the list of file names on RDA Server according to the order they are given per option -`HF <section5.2.rst#HF>`_. Reordering filelist can be also accomplished by giving option -`ON <section5.1.rst#ON>`_ (-OrderNames), which tells Action -`SH <section3.4.5.rst>`_ to reorder all the files of given dataset and the involved groups
   * - -(`SC|SetChecksum <section4.rst#SC>`_)
     - evaluates the md5 checksum values for the help files and saves them into RDADB

  One or multiple local file names can be provided per option -`LF <section5.2.rst#LF>`_ (-LocalFile)
  for this action to work. If option -`LF <section5.2.rst#LF>`_ is given on command line, '*' and '?'
  can be used in local file names for wildcard match. File names must include
  relative or absolute paths if local data files are not located in the
  directory where **dsarch** is started. The local file names are gathered
  recursively following the sub-directory tree if a local directory per `Info <section5.rst>`_
  option -`LD <section5.1.rst#LD>`_ (-LocalDirectory) is present.

  Local file names are used as default for Saved file names unless they are
  explicitly given per option -`SF <section5.2.rst#SF>`_ (-SavedFile). The original local file names,
  including paths, are used if `Mode <section4.rst>`_ option -`KP <section4.rst#KP>`_ (-KeepLocalPath) is specified.

  The number of values passed in per `Info <section5.rst>`_ options must be the same as the number
  of local file names provided, except for the `Info <section5.rst>`_ options that are allowed to
  pass in single values, such as options -`DF <section5.2.rst#DF>`_ (-DataFormat), -`AF <section5.2.rst#AF>`_ (-ArchiveFormat),
  and -`HT <section5.2.rst#HT>`_ (-HelpFileType).

  The location flag is provided via option -`LC <section5.2.rst#LC>`_ (-Location). The defualt value
  is 'B' for archiving a help file onto both Web Disk and Object Store.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
