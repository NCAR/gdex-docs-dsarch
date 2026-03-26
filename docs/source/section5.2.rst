
.. _section5.2:

5.2 - Multi-Value Info Options
=====================

  A multi-value Info option is used to pass multiple values for one Info option
  into **dsarch**. At lease one value must follow each multi-value option.


.. _AF:

Info Option -**AF** (-**ArchiveFormat**) (Aliases: -**FileFormat**, -**ExternalFormat**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for file
  archiving formats of data files being archived onto RDA Servers. The file
  archive format indicates post process of a data file. Option values, 'BI' -
  binary blocked, 'C1' or 'CH' - ASCII/character blocked, can be passed
  in for COS block information of data files; 'TAR' means a tarred file, 'Z'
  means a compressed file and 'GZ' means a gzipped file, and 'BZ2' means a file
  is compressed via bzip2. 'C1.TAR.GZ', for example, means a file is COS ASCII
  blocked and then tarred and then gzipped; the order is important. The maximum
  length of format string is 10. Additional characters are truncated for length
  longer than 10.


.. _BD:

Info Option -**BD** (-**BeginDate**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for begin date of data files of a given group or the whole
  dataset, or begin date of a version control record.


.. _BF:

Info Option -**BF** (-**BackupFlag**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

flags set in Datasets and/or groups to control Quasar
  auto-backup activities; N-No auto-backup (default value for Datasets),
  B-auto-Backup onto Quasar backup endpoint, D-auto-Backup onto Quasar backup&drdata
  endpoints, P-the same Backup flags set in parent groups (default values in groups,
  and parent group index 0 means to follow flags in datasets).


.. _BP:

Info Option -**BP** (-**BatchProcess**) (Aliases: -**d**, -**DelayedMode**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

delayed mode execution. When
  it presents, the **dsarch** command is not executed right way, but the command
  information is recorded into RDADB instead and the command is executed later
  by the centralized daemon 'dscheck'. One or multiple host names can be specified
  after option -`BP <#BP>`_ to force the **dsarch** command be executed on or not on the hosts.
  For examples, '-d rda-data' to run on host 'rda-data'; '-d rda-data:rda-web-prod'
  to run on hosts 'rda-data' and 'rda-web-prod'; and '-d \!rda-web-prod:rda-data'
  to run on all configured hosts other than 'rda-web-prod' and 'rda-data'. Character
  '!' needs to be escaped for passing in on command line. A upper limit for number
  of tries can also be passed in with this options, 1 to 99, as '-d 5' for example.
  It default to 2 for command of **dsarch** if not specified. And also dsarch actions,
  -(`AS <section3.4.9.rst>`_|AW|AH|AQ), will be restarted automatically when this option is present, if
  the previous processes are failed due to storage system downs.


.. _BS:

Info Option -**BS** (-**BackStatus**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Quasar Backup File status, a single letter status flag,
  A - files are backed up onto Globus Quasar servers; T - the backup tar files
  are generated, waiting to be archived; and N - backup file records and input
  files for Web/Saved file lists are created, waiting to be tarred.


.. _BT:

Info Option -**BT** (-**BeginTime**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for begin time of data files of a given group or the whole
  dataset, or begin time of a version control record.


.. _DA:

Info Option -**DA** (-**DataAccess**) (Aliases: -**DataAccessflag**, -**FileListFlag**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

(Alias: -DataAccessFlag, -FileListFlag). flags to show web file
  lists at Dataset and/or top group levels; B-Both Filelists,
  C-Complete File List (default value), F-Faceted Browse or N-No File List.


.. _DB:

Info Option -**DB** (-**Debug**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

to turn on debug mode with specified information. This option
  provides up to 3 values, they are Debug Level, debug log file path and debug
  log file name. The debug level is mandatory for this option. It can be a
  single integer value, for example, 1000 means to log debug messages for debug
  levels 1 to 1000; or a range of values, for example, 200-1000 means to log
  debug messages from debug levels 200 to 1000. The default debug file path is
  '$DECSHOME}/dssdb/log' and the default debug file name is 'mydss.dbg'. Provides
  the second and third values for this option to override the default ones
  respectively.


.. _DE:

Info Option -**DE** (-**Description**) (Aliases: -**Desc**, -**Note**, -**FileDesc**, -**FileDescription**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for file
  descriptions of data files. Multiple lines are allowed for a description if it is
  passed in from an input file specified by Info option -`IF <#IF>`_ (-InputFile). On
  commandline, a single line description with spaces between words must be quoted
  in 'single quotes'. It presents a version control note if it is used with
  version control Actions.


.. _DF:

Info Option -**DF** (-**DataFormat**) (Aliases: -**TF**, -**ContentFormat**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

data content
  format of files being archived onto RDA Servers. This is content format of data
  files. For examples, NetCDF, IMMA and etc.

  A default data format can be set for a given dataset. It is used for archive
  actions when the data format is not provided explicitly.


.. _DN:

Info Option -**DN** (-**DOINumber**) (Aliases: -**DOI**, -**DOIName**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for DOI, a Digital Object
  Identification, of a given dataset for public users to reference against.


.. _DO:

Info Option -**DO** (-**DisplayOrder**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for display order indices of files of a given group,
  or of the whole dataset if no groups are set for the dataset. This Info option
  is ignored if `Mode <section4.rst>`_ option -`RO <section4.rst#RO>`_ (-Reorder) is present.


.. _ED:

Info Option -**ED** (-**EndDate**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for end date of data files of a given group or the whole
  dataset, or end date of a version control record when it is terminated.


.. _ET:

Info Option -**ET** (-**EndTime**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for end time of data files of a given group or the whole
  dataset, or end time of a version control record when it is terminated.


.. _EV:

Info Option -**EV** (-**ExternalVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

external version number. It is only used if a public
  version number is used for a dataset; otherwise it is defaulted to empty.


.. _FD:

Info Option -**FD** (-**FileDate**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for date of a data file last modified on.


.. _FF:

Info Option -**FF** (-**FileFlag**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

File type flag, F for File and P for Path.


.. _FS:

Info Option -**FS** (-**FileStatus**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

File status, a single letter status flag, P - show file
  to public users; and I - to show file to specialist only.


.. _FT:

Info Option -**FT** (-**FileTime**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for time of a data file last modified at.


.. _GI:

Info Option -**GI** (-**GroupIndex**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for group indices. This is considered only if a dataset
  is divided further into groups. To make the grouping works, run this
  utility program with action -`SG <section3.3.1.rst>`_ (-SetGroup) for a given dataset before
  archiving files to the dataset. Valid group index values are 1, 2, 3, ....,
  while 0 means no group which is the default index value.

  If this option is omitted for file archiving options -`AS <section3.4.9.rst>`_ or -`AW <section3.4.10.rst>`_ of a dataset
  with groups, pattern matching logic is automatically processed; a group index
  is determined by matching the local file name to group patterns previously
  saved in RDADB.


.. _GL:

Info Option -**GL** (-**GroupLevel**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

number of group/subgroup levels to be displayed in the
  group lists. It defaults to 2. Set it to -2 to display one level initially
  but the group list can be expanded up to 2 levels if the subgroups exist.


.. _GN:

Info Option -**GN** (-**GroupName**) (Alias: -**GroupID**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

a short string, up to 20 characters, for
  group ID name. Group names can be set into RDADB for a given dataset per
  action -`SG <section3.3.1.rst>`_ (-SetGroup). If set, they can be provided per this option to
  identify group indices, and in addition, they are displayed on webpages of
  Web filelists instead of group indices.


.. _GP:

Info Option -**GP** (-**GroupPattern**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

group patterns to match local file names with group
  indices while archiving Saved or Web files. The group patterns from this
  option are saved into RDADB for specified groups of a given dataset per
  action -`SG <section3.3.1.rst>`_ (-SetGroup).


.. _GT:

Info Option -**GT** (-**GroupType**) (Alias: -**GroupDataType**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

set P for Public or I for
  Internal group types. When a group type is set from P to I, all the public
  subgroups under it are set to I recursively, and all the public Web files
  under the groups or its subgroups are set to Internal too.


.. _HF:

Info Option -**HF** (-**HelpFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for Help file names. During Document or software archiving
  per action -`AH <section3.4.11.rst>`_ (-ArchiveHelpFile), the local file names given by option -`LF <#LF>`_
  (-LocalFile) are used as default for the Help file names unless different
  file names are specified by this option.


.. _HT:

Info Option -**HT** (-**HelpFileType**) (Alias: -**HelpType**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Help file types,
  a single letter property flag, D-Document and S-Software. If only one type
  is passed in, all Help files are assumed to be the same type.


.. _ID:

Info Option -**ID** (-**InitialDate**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for date of a Help, Document/Software, file last
  Published/Released on.


.. _IF:

Info Option -**IF** (-**InputFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for input file names; one or multiple file names may be
  given on command line. A input file name must start with dataset number as
  in format of 'dsnnn.n.*' and the dataset number must match the dataset number
  given per option -`DS <section5.1.rst#DS>`_ (-Dataset). This restriction is for prevention that
  specialists archive data files accidentally into a wrong dataset. Input files
  are used to hold all valid options and the associated values of Info options
  that need to be passed in for execution of **dsarch**.

  In a input file, lines start with sign '#' are considered as comments;
  Option Names can be given either short, long or alias names. `Action <section3.rst>`_ and `Mode <section4.rst>`_
  options are given in format of OptionName<!>. Single value Assignment is
  given in format of OptionName<=>OptionValue. One option is given on each line.
  Different setting sign of `Action <section3.rst>`_ and `Mode <section4.rst>`_ options can be provided by Info
  option -AO (-ActOption, default to <!>); and different equal sign of single
  value assignment can be provided by Info option -`ES <section5.1.rst#ES>`_, (-EqualSign, default to
  '<=>'). Multi-value assignments can be given in columns delimited with
  separator specified per option -SP (-Separator, default to '<:>'). It starts
  with a column title line for multi-value option names and the rest holds
  values corresponding to each column titles. The value information stops at
  the end of the file or when a new column name line or another single value
  assignment appears. If the last column is a multi-line value field, an
  additional separator must be appended for each line, including the column
  title line to end lines properly.


.. _IV:

Info Option -**IV** (-**InternalVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

internal version index. It is used to indicate a different
  version of data with minimal changes under the same DOI number. It is defaulted
  to 1 for a version control record with new created DOI number.


.. _KV:

Info Option -**KV** (-**KeyValue**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

to set specialist defined key/value pairs via action -`SD <section3.1.1.rst>`_
  (-SetDataset). These special key/value pairs can be viewed per option -`GD <section3.1.2.rst>`_
  (-GetDataset). Specialists can record key/value pair information for
  specified datasets for personal or shared information. A key can be up to
  40 characters and a value can be up to 128 characters.


.. _e11:

**EXAMPLE 11. **

Syntax To Set A Key/Value Pair Of 'Test/Test It' For D540000 On
  command line

  dsarch d540000 SD -`KV <#KV>`_ 'test=>test it'

  and to view this pair

  dsarch d540000 GD -`KV <#KV>`_ test

  and to view all available key/value pairs

  dsarch d540000 GD -`KV <#KV>`_ all


.. _LC:

Info Option -**LC** (-**Location**) (Alias: -**LocationFlag**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Storage localtion flags for CGD data,
  Web and Saved data files, and Help files, are C-CGD data, G-Glade Disk, O-Object
  Store, and B-Both Storage Systems. For Help files, an additional flag R is for
  Remote URL. This flag is also used in dataset table as web online file access
  location. The valid values are G or O, which mean to access online file on Glade
  or Object Store, respectively.


.. _LF:

Info Option -**LF** (-**LocalFile**) (Aliases: -**LocFile**, -**SourceFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for local file names,
  also called  original or source file names. A local file is a data file that
  is ready to be archived as Saved, Web or Help file. It is later archived
  onto RDA servers according to actions -`AS <section3.4.9.rst>`_ (-ArchiveSavedFile), -`AW <section3.4.10.rst>`_
  (-ArchiveWebFile) or -`AH <section3.4.11.rst>`_ (-ArchiveHelpFile). UNIX wildcard is acceptable if
  given on command line to match multiple local file names.  Absolute or
  relative paths need to be added to the local file names if the data files are
  not located in the directory where this application is running.


.. _MC:

Info Option -**MC** (-**MD5Checksum**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

providing md5 checksum IDs of of the given data files
  on RDA Servers.


.. _ML:

Info Option -**ML** (-**MetaLink**) (Alias: -**MetadataLink**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

providing a link to dataset, group or
  file level content metadata page. This link is normally auto-generated from
  inside of utility program **gatherxml**, which is triggered when `Mode <section4.rst>`_ option
  -`GX <section4.rst#GX>`_ is present for actions of archiving or setting Web data files.

  Although it is not recommended, specialists are allowed, under certain
  circumstances, to generate their own detail content meta data and put a link
  via this option, and it overrides the auto-generated link.


.. _ND:

Info Option -**ND** (-**NoteDocument**) (Aliases: -**DocumentNote**, -**DescDocument**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for Document
  descriptions of a given dataset.


.. _NI:

Info Option -**NI** (-**NoteInternal**) (Aliases: -**InternalNote**, -**DescInternal**, -**DI**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for internal
  data descriptions of a given group or the dataset itself.


.. _NS:

Info Option -**NS** (-**NoteSoftware**) (Aliases: -**SoftwareNote**, -**DescSoftware**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for Software
  descriptions of a given dataset.


.. _NW:

Info Option -**NW** (-**NoteWeb**) (Aliases: -**WebNote**, -**DescWeb**, -**DW**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for descriptions
  of Web data on RDA Server of a given group or the dataset itself.


.. _OB:

Info Option -**OB** (-**OrderBy**) (Alias: -**OrderByPattern**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

temporal patterns used to order
  filelist according to the string values of field names specified per
  option -`ON <section5.1.rst#ON>`_ (-OrderNames). 'YYYYmon', for example, means the order should
  be based on on 4 digit year and three letter lowercase month names as 'jan',
  'feb', and etc. Check option -`ON <section5.1.rst#ON>`_ (-OrderNames) for example of ordering
  files by temporal patterns.


.. _OD:

Info Option -**OD** (-**OriginDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for an original dataset number; used for action
  -`MV <section3.4.14.rst>`_ (-MoveFile).


.. _OG:

Info Option -**OG** (-**OriginGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for original group indices, used for action -`CG <section3.3.4.rst>`_
  (-ChangeGroup) to change group indices of specified data files of a
  given dataset. Check option -`GI <#GI>`_ (-GroupIndex) for more information.


.. _OT:

Info Option -**OT** (-**OriginType**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

original web file types. This option is used only
  for action -`MV <section3.4.14.rst>`_ (-MoveFile) to move files by changing file types.


.. _PI:

Info Option -**PI** (-**ParentIndex**) (Alias: -**ParentGroupIndex**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for parent group indices.
  This is considered only if a group is divided further into subgroups.
  Subgrouping can continue going down to as many levels as needed.


.. _QF:

Info Option -**QF** (-**QuasarFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for Quasar backup file names. During Quasar backing up
  per action -`AQ <section3.4.12.rst>`_ (-ArchiveQuasarFile), a quasar file name must be specified
  by this option.


.. _QT:

Info Option -**QT** (-**QuasarFileType**) (Aliases: -**QuasarType**, -**BackupType**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Quasar file
  types, a single letter property flag, B-Quasar Backup only and D-Quasar
  Backup and Drdata.


.. _RF:

Info Option -**RF** (-**OriginFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for original Web file names used for action -`MV <section3.4.14.rst>`_
  (-MoveFile) to move data files from one dataset specified by option -`OD <#OD>`_
  (-OriginDataset) to a new dataset specified by option -`DS <section5.1.rst#DS>`_ (-Dataset).
  Set this option only when original file names are different from the new
  ones.


.. _SF:

Info Option -**SF** (-**SavedFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for Saved file names. During Saved data archiving
  per action -`AS <section3.4.9.rst>`_ (-ArchiveSavedFile), the local file names given by option -`LF <#LF>`_
  (-LocalFile) are used as default for the saved file names unless different
  file names are specified by this option.


.. _SP:

Info Option -**SP** (-**SavedPath**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for saved file paths relative to the saved data home directory.
  For action -`AS <section3.4.9.rst>`_ (-ArchiveSavedFile), if this option is not specified, the path
  values previously saved in RDADB for given dataset, and groups if specified,
  are used. For action -`SG <section3.3.1.rst>`_ (-SetGroup) and -`SD <section3.1.1.rst>`_ -(-SetDataset), path values given by
  this option are saved into RDADB for the specified groups and dataset.

  The group saved paths matching well with groups are important for NCAR internal
  users to list group/file information on the the data storage disks directly via
  utility program 'rdals'. One and only one single directory must be assign to a
  top level group, one additional directory should be appended for each sub-group
  down. A web path relative to the web data home directory is saved in each group
  record. In this way, the web path values match exactly the physical directory
  tree of a specified dataset.


.. _SR:

Info Option -**SR** (-**Source**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for source of a Help file contributed from.


.. _ST:

Info Option -**ST** (-**SavedFileType**) (Aliases: -**SavedType**, -**SavedArchiveType**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Saved file types,
  a single letter property flag, P-Primary, R-Original, W-Work, S-Scratch,
  and V-Version control. If only one type is passed in, all Saved files are
  assumed to be the same type.


.. _SZ:

Info Option -**SZ** (-**Size**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for file sizes in bytes. During data archiving the sizes of data
  files are gathered dynamically from the local files given per option -`LF <#LF>`_
  (-LocalFile) unless the sizes are specified by this option otherwise.


.. _TG:

Info Option -**TG** (-**TopGroupIndex**) (Alias: -**TopGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

top group index values for Saved/Web
  files belong to the top group or its subgroups.


.. _TI:

Info Option -**TI** (-**Title**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for dataset or group titles. Dataset title is readonly for
  **dsarch**; use Metadata Editor to modify it.


.. _TL:

Info Option -**TL** (-**ThreddLink**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

providing a link to file level Thredd Catalog page.
  Set this value to Y if Thredd Catalog information is gathered for a file.


.. _VI:

Info Option -**VI** (-**VersionIndex**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

version control index to have DOI/Version control on
  a given dataset.


.. _VT:

Info Option -**VT** (-**VersionStatus**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

version control status, A-Active, P-Pending and H-History.


.. _WF:

Info Option -**WF** (-**WebFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for file names on RDA Servers. During Web data archiving
  per action -`AW <section3.4.10.rst>`_ (-ArchiveWebFile), the local file names given by option -`LF <#LF>`_
  (-LocalFile) are used as default for the Web file names unless different
  file names are specified by this option.


.. _WH:

Info Option -**WH** (-**WebHome**) (Alias: -**WebDataHome**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

(Alias: -WebDataHome), for web Web data home directory
  other than the default location. Use -`SD <section3.1.1.rst>`_ -(-SetDataset), to set web data
  home directory into RDADB for the specified dataset.


.. _WP:

Info Option -**WP** (-**WebPath**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for web file paths relative to the Web data home directory. For
  action -`AW <section3.4.10.rst>`_ (-ArchiveWebFile), if this option is not specified, the path
  values previously saved in RDADB for given dataset, and groups if specified,
  are used. For action -`SG <section3.3.1.rst>`_ (-SetGroup) and -`SD <section3.1.1.rst>`_ -(-SetDataset), path values given by
  this option are saved into RDADB for the specified groups and dataset.

  The group web paths matching well with groups are important for NCAR internal
  users to list group/file information on the the data storage disks directly via
  utility program 'rdals'. One and only one single directory must be assign to a
  top level group, one additional directory should be appended for each sub-group
  down. A web path relative to the web data home directory is saved in each group
  record. In this way, the web path values match exactly the physical directory
  tree of a specified dataset.


.. _WT:

Info Option -**WT** (-**WebFileType**) (Aliases: -**WebType**, -**WebArchiveType**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

web file types,
  D-Data and N-NCAR Data. If only one type is passed in, all Saved files are
  assumed to be the same type.


.. _WU:

Info Option -**WU** (-**WebURL**) (Aliases: -**URL**, -**WebAddress**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Web URL for a Help file to link it to
  a remote web server, such as github.com. This option works with `Action <section3.rst>`_ -`SH <section3.4.5.rst>`_
  (-SetHelpFile) to create a remote Document or Software file record in RDADB
  without local copy on RDA Servers.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
