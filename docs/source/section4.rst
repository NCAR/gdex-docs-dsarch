
.. _section4:

4 - MODE OPTIONS
=====================

Use proper Mode options to modify behaviors of `Action <section3.rst>`_ options. Mode options
are all optional. No value is allowed to be passed in following any Mode option.


.. _BG:

Mode Option -**BG** (-**BackGround**) (Alias: -**b**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

background process. When it presents
  screen display is turned off for both standard outputs and errors.


.. _CL:

Mode Option -**CL** (-**CleanLocal**) (Aliases: -**CleanLocFile**, -**CleanLocalFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present for
  archiving actions -`AS <section3.4.9.rst>`_, or -`AW <section3.4.10.rst>`_, cleans the local files after they are all archived
  successfully. If local files are staged temporarily in sub-directories, the
  sub-directories can be removed too after all the local files are cleaned inside
  them. Add `Info <section5.rst>`_ option -`DD <section5.1.rst#DD>`_ DirectoryLevel to tell how many level of the local
  empty directories to be removed.


.. _DX:

Mode Option -**DX** (-**DeleteXML**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

if present, calls **dcm** to delete file content metadata
  of given Web files for actions -`SW <section3.4.3.rst>`_ (-SetWebFile). This is the default Mode for
  action -`DL <section3.4.15.rst>`_ (-Delete) of Web files provided via -`WF <section5.2.rst#WF>`_ (-WebFile).


.. _EM:

Mode Option -**EM** (-**EmailNotice**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

sends an email notice to the specialist who executes the
  dsarch for certain actions after a action is finished successfully or aborts
  abnormally. The Actions working with this Mode option include -`AS <section3.4.9.rst>`_, -`AW <section3.4.10.rst>`_,, -`AH <section3.4.11.rst>`_,
  -`AQ <section3.4.12.rst>`_, -`SS <section3.4.1.rst>`_, -`SW <section3.4.3.rst>`_, -`SH <section3.4.5.rst>`_, -`SQ <section3.4.7.rst>`_, -`RQ <section3.4.13.rst>`_, -`MV <section3.4.14.rst>`_ and -`DL <section3.4.15.rst>`_. An email notice includes errors
  happening during the action and a brief summary to show the action progress.
  This option is ignored if option -d is present.

  Specialists need to be cautious of adding this Mode option to run dsarch.
  If you run dsarch to archive many files with one at a time, you will receive
  one email for each file. To make it work better, you include all the files
  you want to process into a single input file and run dsarch with option -`EM <#EM>`_
  against the input file. This way you receive a single email notice instead.


.. _FO:

Mode Option -**FO** (-**FormatOutput**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

if present, formats column output results for get
  actions.  A same width, evaluated dynamically, is applied for all values of a
  given field.


.. _GF:

Mode Option -**GF** (-**GrowingFile**) (Alias: -**GrowingDataFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

if present, `Action <section3.rst>`_ -`AW <section3.4.10.rst>`_ (-ArchiveWebFile) will allow
  existing Web files being overridden although the data files are
  under DOI/Version control already. Normally an archived data file can not
  changed if it is linked to a version control record. This Mode option
  indicates that the data file is a growing one and needs to be updated.
  If `Action <section3.rst>`_ -`AW <section3.4.10.rst>`_ of **dsarch** is controlled by configuration of `dsupdt <https://gdex-docs-dsupdt.readthedocs.io/en/latest/index.html>`_, a
  growing file is automatically detected and this Mode option is added to the
  **dsarch** command as needed.


.. _GX:

Mode Option -**GX** (-**GatherXML**) (Alias: -**Grid2XML**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

if present, calls **gatherxml** to
  evaluate file content metadata of archived Web files. This is the default
  Mode for action -`MV <section3.4.14.rst>`_ (-MoveFile) for Web files, to call **rcm** to move the
  file content metadata too.


.. _GZ:

Mode Option -**GZ** (-**GMTZone**) (Aliases: -**GMT**, -**GreenwichZone**, -**UTC**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

uses GMT dates/times as
  controlling times for archiving actions, instead of mountain time.


.. _KM:

Mode Option -**KM** (-**KeepMetadata**) (Alias: -**KeepMeta**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for actions -`MV <section3.4.14.rst>`_ (-MoveFile) with
  option -`TS <#TS>`_ (-ToSaved) to keep the metadata record for later use after
  the web file is moved to savefile.


.. _KP:

Mode Option -**KP** (-**KeepPath**) (Alias: -**KeepLocalPath**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-`AW <section3.4.10.rst>`_
  (-ArchiveWebFile) and -`AH <section3.4.11.rst>`_ (-ArchiveHelpFile) to archive Saved/Web/Help files with
  the same file names as the local ones specified by -`LF <section5.2.rst#LF>`_ (-LocalFile).  A relative
  path is reta8ined if it is part of a local file name. Options -`SP <section5.2.rst#SP>`_ (-SavedPath)
  and -`WP <section5.2.rst#WP>`_ (-WebPath) are ignored if -`KP <#KP>`_ is given. This Mode option is ignored if
  Save/Web/Help file names are specified per options -`SF <section5.2.rst#SF>`_ (-SavedFile), -`WF <section5.2.rst#WF>`_ (-WebFile),
  and -`HF <section5.2.rst#HF>`_ (-HelpFile), respectively.


.. _MD:

Mode Option -**MD** (-**MyDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

allows a specialist to update dataset/group/file


.. _NE:

Mode Option -**NE** (-**NoEmail**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

does not send email notice to the specialist for failed action.


.. _NT:

Mode Option -**NT** (-**NoTrim**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

skips trimming of spaces and comments from input values to
  speed up reading input file(s).


.. _NV:

Mode Option -**NV** (-**NewVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

adds a new version control record for a specified dataset
  if this Mode option is present for `Action <section3.rst>`_ -`SV <section3.2.1.rst>`_ (-SetVersion).


.. _OE:

Mode Option -**OE** (-**OverrideExist**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

if present, overrides an existing file.


.. _PE:

Mode Option -**PE** (-**ShowPeriod**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

shows period information for dataset, and groups if provided,
  for action -`SD <section3.1.1.rst>`_ (-SetDataset).


.. _RA:

Mode Option -**RA** (-**RetryArchive**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

deprecated, does not do anything.


.. _RD:

Mode Option -**RD** (-**RemoveDir**) (Aliases: -**RemoveDirectory**, -**RemoveEmptyDir**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

it works with
  Actions -`DL <section3.4.15.rst>`_, -`SS <section3.4.1.rst>`_ and -`SW <section3.4.3.rst>`_ to remove empty directories for a specified dataset,
  and groups if specified.

  If empty directories are not cleaned after deleting files. Use Actions -`SS <section3.4.1.rst>`_ or
  -`SW <section3.4.3.rst>`_ with this Mode option, without Saved or Web file names specified, to clean
  the empty Web or HPSS directories, respectively for a given dataset, and
  groups if specified.


.. _RG:

Mode Option -**RG** (-**RecursiveGroup**) (Alias: -**RepeatGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present, gathers subgroups
  and file information in subgroups recursively for actions -`GG <section3.3.2.rst>`_ (-GetGroup) and
  -`GS <section3.4.2.rst>`_/GW (-GetSavedFile/GetWebfile), respectively. Group index must be provided
  explicitly via `Info <section5.rst>`_ option -`GI <section5.2.rst#GI>`_ (-GroupIndex) for this Mode option to work.


.. _RN:

Mode Option -**RN** (-**RelativeName**) (Aliases: -**RelativePathName**, -**RelativeFileName**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for action -`GS <section3.4.2.rst>`_ (-GetSavedFile) and -`GW <section3.4.4.rst>`_ (-GetWebFile) to
  show a file name with path relative to the Saved and Web paths set for
  the dataset or group, respectively.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present, resets the display orders
  of the given Saved/Web/Help/Quasar file lists as the orders the data files are
  given for actions -`SS <section3.4.1.rst>`_ (-SetSavedFile), -`SW <section3.4.3.rst>`_ (-SetWebFile), -`SH <section3.4.5.rst>`_ (-SetHelpFile),
  and -`SQ <section3.4.7.rst>`_ (-SetQuasarFile), respectively. Another way of reordering the data files
  is to provide explicitly order index values per `Info <section5.rst>`_ option -`DO <section5.2.rst#DO>`_ (-DisplayOrder).

  Specify what fields to order on per option -`ON <section5.1.rst#ON>`_ (-OrderNames) to order the
  files accord for the whole datasets or individual groups.  Check option -`ON <section5.1.rst#ON>`_
  for examples of ordering Files.


.. _RS:

Mode Option -**RS** (-**GXRSOptions**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

works with Mode option -`GX <#GX>`_ (-GatherXML) to pass option
  R and S to command gatherxml for speeding up.


.. _RT:

Mode Option -**RT** (-**ResetTIndex**) (Alias: -**ResetTopGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for setting actions to reset
  the top group index for Saved or Web files for dataset, and groups if
  specified.


.. _SC:

Mode Option -**SC** (-**SetChecksum**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

if presents, evaluates the md5 checksum values for data
  files on RDA Servers and saves them into RDADB


.. _TO:

Mode Option -**TO** (-**TarOnly**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

works with `Action <section3.rst>`_ -`AQ <section3.4.12.rst>`_ (-ArchiveQuasarFile) to tar the given
  Saved and/or Web files only, without physically backing up the Quasar file
  onto the Globus Quasar Server.


.. _TS:

Mode Option -**TS** (-**ToSaved**) (Aliases: -**ToSavedFile**, -**MovedToSaved**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present for `Action <section3.rst>`_ -`MV <section3.4.14.rst>`_ to
  move Web files to Saved files.


.. _TT:

Mode Option -**TT** (-**TotalSummary**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present, gets the statistic summary information
  for `Action <section3.rst>`_ options -`GS <section3.4.2.rst>`_ (-GetSavedFile) and -`GW <section3.4.4.rst>`_ (-GetWebFile).


.. _TW:

Mode Option -**TW** (-**ToWeb**) (Aliases: -**ToWebFile**, -**MovedToWeb**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present for `Action <section3.rst>`_ -`MV <section3.4.14.rst>`_ to
  move Saved files to Web files.


.. _UZ:

Mode Option -**UZ** (-**UnzipData**) (Aliases: -**Uncompress**, -**UncompressData**, -**Unzip**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

uncompresses online data
  with one of the uncompressing utilities, 'gunzip', 'uncompress', 'unzip'
  or 'bunzip', according to the file name extensions of ".gz', '.Z', '.zip'
  or '.bz2', respectively


.. _WC:

Mode Option -**WC** (-**WithChecksum**) (Aliases: -**ValidateChecksum**, -**WithMD5**, -**ValidateMD5**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present, checks the MD5 checksums in addition to
  the data file sizes for online data files on RDA Server.


.. _WM:

Mode Option -**WM** (-**WithMetadata**) (Alias: -**WithMeta**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for setting actions to reset the dataset/group level
  content metadata for action -`SD <section3.1.1.rst>`_/SG (-SetDataset/SetGroup).


.. _WN:

Mode Option -**WN** (-**WithFileNumber**) (Alias: -**WithNumber**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for setting actions to reevaluate and reset the
  Saved or Web file counts for dataset, and groups if specified. These file
  counts can also be viewed for action -`GD <section3.1.2.rst>`_ (-GetDataset) if this Mode option is
  preset.


.. _XC:

Mode Option -**XC** (-**CrossCopy**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

works with action -`AW <section3.4.10.rst>`_/-AS to cross copy data files between
  Web/Saved files on Glade disk and Object files on Object store.


.. _XM:

Mode Option -**XM** (-**CrossMove**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

works with action -`AW <section3.4.10.rst>`_/-AS to cross move data files between
  Web/Saved files on Glade disk and Object files on Object store. This Mode option
  is different from -`XC <#XC>`_ that the original files are removed.


.. _ZD:

Mode Option -**ZD** (-**ZipData**) (Aliases: -**Compress**, -**CompressData**, -**Zip**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

when present, Actions -`AS <section3.4.9.rst>`_
  (-ArchiveSavedFile) and -`AW <section3.4.10.rst>`_ (-ArchiveWebFile) compress online data with one
  of the compressing utilities,  'gzip', 'compress', 'zip' and 'bzip', according
  to the archiving format 'GZ', 'Z', 'ZIP' or 'BZ2' provided per option -`AF <section5.2.rst#AF>`_
  (-ARchiveFormat), respectively. If the original data files are compressed already,
  this Mode option is ignored if the same compression, and the files are uncompressed,
  before compressing, with one of the uncompressing utilities, 'gunzip', 'uncompress',
  'unzip' or 'bunzip', according to the file name extensions of ".gz', '.Z', '.zip'
  or '.bz2', respectively.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
