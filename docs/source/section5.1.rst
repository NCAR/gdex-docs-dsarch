
.. _section5.1:

5.1 - Single-Value Info Options
=====================

  A single-value Info option is used to pass one value into this application.
  One value, and one only, must follow a single-value option; otherwise an
  error message is displayed if no value or more than one value passed in.


.. _AL:

Info Option -**AL** (-**AsyncLimit**) (Alias: -**AsynchronousLimit**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

provides a value of the
  maximum number of background processes for 'cp' and **gatherxml** calls. This
  option is ignored for PBS batch jobs.


.. _AO:

Info Option -**AO** (-**ActionOption**) (Alias: -**ActOption**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 for setting `Action <section3.rst>`_ and `Mode <section4.rst>`_ options in input files. It is
  default to '<!>'.


.. _BL:

Info Option -**BL** (-**ButtonLimit**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

controlling limit of available file count in filelist
  to show click buttons for download scripts. The default number is 2.


.. _DD:

Info Option -**DD** (-**DeleteDir**) (Aliases: -**DeleteDirLevel**, -**DeleteEmptyDir**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

it works with
  Actions -`DL <section3.4.15.rst>`_ (-Delete) or -`MV <section3.4.14.rst>`_ (-MoveFile) for removing how many level of
  empty directories after all files inside are deleted or moved. It works
  with `Mode <section4.rst>`_ option -`CL <section4.rst#CL>`_ too for Actions -`AS <section3.4.9.rst>`_ and -`AW <section3.4.10.rst>`_ to remove empty local
  directories after the local files inside of them are all cleaned.


.. _DS:

Info Option -**DS** (-**Dataset**) (Aliases: -**Dsid**, -**DatasetID**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for a dataset number, or called dataset ID in form as
  [a-z]NNNNNN. It is mandatory for most actions.


.. _DV:

Info Option -**DV** (-**Divider**) (Aliases: -**Delimiter**, -**Separater**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 delimiter for separating
  columns of multi-value Info options in input files. It is default to '<:>'.


.. _ES:

Info Option -**ES** (-**EqualSign**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for an equal sign of assigning one value to either a
  single-value option or multi-value option in input files. It is defaulted
  to '<=>'.


.. _FL:

Info Option -**FL** (-**FileLimit**) (Alias: -**FileCountLimit**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

sets limit for how many files
  can be displayed on a single web page of static filelists. Files from
  multiple groups may be displayed on a single page if the total file count
  is lower than this limit, while files from a single group may be split into
  sub-filelists if the file count is beyond this limit. It defaults to 2000
  and specialists can reset it to a different value for a specified dataset
  via `Action <section3.rst>`_ -`SD <section3.1.1.rst>`_ (-SetDataset).


.. _FN:

Info Option -**FN** (-**FieldNames**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for a string of single letter field names. Values of
  the selected fields are retrieved per actions -`GD <section3.1.2.rst>`_ (-GetDataset),
  -`GG <section3.3.2.rst>`_ (-GetGroup), -`GS <section3.4.2.rst>`_ (-GetSavedFile), -`GW <section3.4.4.rst>`_ (-GetWebFile), -`GH <section3.4.6.rst>`_ (-GetHelpFile),
  and -`GQ <section3.4.8.rst>`_ (-GetQuasarFile). Values of default fields are retrieved according
  to what GET action is specified. Valid field names are listed in corresponding
  Get action sections.


.. _LD:

Info Option -**LD** (-**LocalDirectory**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

provides a single local directory, file names under
  the directory, and the sub-directories recursively if any, are all collected
  as local files


.. _LL:

Info Option -**LL** (-**LocalFileList**) (Alias: -**LocalList**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

provides a single file name and the file holds a list of
  file names, one file name on each line. These file names are used as the local
  file names


.. _LN:

Info Option -**LN** (-**LoginName**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

login name of the current user; it defaults to the current
  login DECS specialist who starts execution of **dsarch**. Set this option if you
  try to run this utility for a specialist other than yourself. Normally this
  is set when this application is started by a daemon or as a cron job. Be
  careful of using this option since it might override the currently information
  of dataset/groups/files saved by other specialists in RDADB.


.. _OF:

Info Option -**OF** (-**OutputFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

leading an output file name into which the output result
  of this application is dumped. Output file format is similar to the format of
  the input files. If this option is not given, the result is displayed on
  screen.


.. _ON:

Info Option -**ON** (-**OrderNames**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for a string of single letter field names use to order
  the results of GET actions, -`GG <section3.3.2.rst>`_ (-GetGroup), -`GS <section3.4.2.rst>`_ (-GetSavedFile), -`GW <section3.4.4.rst>`_
  (-GetWebFile), -`GH <section3.4.6.rst>`_ (-GetHelpFile), and -`GQ <section3.4.8.rst>`_ (-GetQuasarFile). Upper case is
  for Ascending order while lower case is for Descending order. This option also
  force reordering of files in individual groups if any file information is modified
  per `Action <section3.rst>`_ options -`AS <section3.4.9.rst>`_ (-ArchiveSavedFile), -`AW <section3.4.10.rst>`_ (-ARchiveWebFile), -`SS <section3.4.1.rst>`_
  (-SetSavedFile), -`SW <section3.4.3.rst>`_ (-SetWebFile), -`DL <section3.4.15.rst>`_ (-DeleteFile) and -`MV <section3.4.14.rst>`_ (MoveFile).

  Web filelists of specified dataset and groups can also be accomplished per
  `Action <section3.rst>`_ -`SW <section3.4.3.rst>`_ (-SetWebFile) with presenting option -`ON <#ON>`_, as

| **dsarch** dsnnn.n -`SW <section3.4.3.rst>`_ -`ON <#ON>`_ OrderNameString [-`GI <section5.2.rst#GI>`_ GroupIndices]

  Without specified group indices, all the files within or without groups
  will all be reordered.


.. _PO:

Info Option -**PO** (-**PatternOffset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

given for string offset of pattern matches while
  assigning group indices to given Saved or Web files by matches the file
  names to given group wildcard patterns for file set/archive actions.
  This is a mandatory Info option for matching group indices of files recorded
  in RDADB already. A binary search is used for pattern matching if an value of
  >= 0 is provided; while a simple linear search is used if a value of -1 is
  provided. Value of -1 is defaulted if this option is not provided for matching
  group index for a file that is not recorded in RDADB yet.


.. _QS:

Info Option -**QS** (-**QsubOptions**) (Alias: -**PBSOptions**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

(Alias: -PBSOptions), specifies options to execute dsarch
  as a batch job via qsub on PBS nodes. The qsub options must be quoted when prsented
  on command line, such as, -`QS <#QS>`_ '-l walltime=12:00:00'.


.. _AO:

Info Option -**AO** (-**ActionOption**) (Alias: -**ActOption**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 for setting `Action <section3.rst>`_ and `Mode <section4.rst>`_ options in input files. It is
  default to '<!>'.


.. _UD:

Info Option -**UD** (-**UseDSARCH**) (Alias: -**UseRDADB**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

for flag of using DSARCH to control the
  given dataset. A value out of 'N', 'Y', 'I', 'P', or 'W' is saved in RDADB
  for a given dataset per action -`SD <section3.1.1.rst>`_ (-SetDataset). A value other than 'N', at
  least 'Y', must be set for a dataset before it can manipulated by **dsarch**.
  'Y' means the the dataset is ready to be modified by **dsarch**.  'I', 'P',
  and 'W' mean that the dataset/group/file information of the specified dataset
  is ready to be published to web server for internal only, publicly, and Web
  file list only, correspondingly.


.. _VS:

Info Option -**VS** (-**ValidSize**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

a minimal size for a file to be valid for archiving process.
  It defaults to 100 bytes and can be reset on command line with the update actions.


.. _WI:

Info Option -**WI** (-**WaitInternval**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

it works for the background processes. When the number of
  background processes reaches the process limit, this option value tells **dsarch**
  to wait this period of time before checking if any background process is finish,
  so that a new background process can be started for next waiting one.

  It can be provided to set a different wait interval, such as Second, Minute,
  Hour or Day. For example, '-`WI <#WI>`_ 5M' is for 5 minutes. A digital value only
  assumes a unit of Second, and '-`WI <#WI>`_ 300' means 300S, for example.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
