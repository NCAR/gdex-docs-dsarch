
.. _section5.1:

5.1 - Single-Value Info Options
=================================

A single-value Info option accepts exactly one value. Providing no
value or more than one causes an error.


.. _AL:

Info Option -**AL** (-**AsyncLimit**) (Alias: -**AsynchronousLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the number of
processes that run at the same time. For :ref:`-AW <AW>`, :ref:`-AH <AH>` and :ref:`-AS <AS>` (also with
:ref:`-XC <XC>`/-XM, and :ref:`-AQ <AQ>` -XC) and for :ref:`-MV <MV>` (also with :ref:`-TS <TS>`/-TW), up to this
many child processes copy, cross copy or move the files in a first
pass; a second pass then checks each one, redoes any that failed,
deletes the sources of a cross move (:ref:`-XM <XM>`), and sets the file records
as usual. It also caps the **gatherxml** and **dcm** calls run in the
background, such as for :ref:`-GX <GX>` with :ref:`-AW <AW>` or :ref:`-SW <SW>`. Other actions, such as
:ref:`-SS <SS>`, run one process and ignore it. Works with :ref:`-BP <BP>` (-d) too: when
the action can use it, the PBS batch job gets one cpu and 1gb of
memory per process (select=1:ncpus=N:mem=Ngb) unless :ref:`-QS <QS>` already
requests select, ncpus or mem.


.. _AO:

Info Option -**AO** (-**ActionOption**) (Alias: -**ActOption**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the token that marks
:ref:`Action <section3>` and :ref:`Mode options <section4>` in input files. Defaults to '<!>'. Change
this if your input data contains the default token.


.. _BL:

Info Option -**BL** (-**ButtonLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the minimum file count at which download
script buttons appear on file list web pages. Defaults to 2.


.. _DD:

Info Option -**DD** (-**DeleteDir**) (Aliases: -**DeleteDirLevel**, -**DeleteEmptyDir**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

how
many levels of empty parent directories to prune after files are
deleted or moved. Applies to :ref:`-DL <DL>`, :ref:`-MV <MV>`, and :ref:`-CL <CL>` (when used with :ref:`-AS <AS>`
or :ref:`-AW <AW>`).


.. _DS:

Info Option -**DS** (-**Dataset**) (Aliases: -**Dsid**, -**DatasetID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the target dataset ID (format: [a-z]NNNNNN).
Required by almost all actions.


.. _DV:

Info Option -**DV** (-**Divider**) (Aliases: -**Delimiter**, -**Separater**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the column
separator used for multi-value Info options in input files.
Defaults to '<:>'.


.. _ES:

Info Option -**ES** (-**EqualSign**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the token used to assign a value to an option
in input files (e.g., 'Dataset<=>d123456'). Defaults to '<=>'.


.. _FL:

Info Option -**FL** (-**FileLimit**) (Alias: -**FileCountLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file count
threshold for static file list pages. Groups whose combined count
falls below this limit are shown together on one page; a group
whose count exceeds it is split across multiple sub-pages. Defaults
to 2000.


.. _FN:

Info Option -**FN** (-**FieldNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a compact string of single-letter codes that
selects which fields to include in GET action output. Default
codes are listed in each action's section; use ALL to retrieve
every available field.


.. _LD:

Info Option -**LD** (-**LocalDirectory**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a local directory to source files from.
All files within it and any sub-directories are collected
recursively.


.. _LL:

Info Option -**LL** (-**LocalFileList**) (Alias: -**LocalList**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a plain-text file listing local file names
to process, one name per line.


.. _LN:

Info Option -**LN** (-**LoginName**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the login name to attribute the action to.
Defaults to the current user. Use this when running on behalf of
another specialist or from an automated process (daemon or cron
job). Use with care — it affects which records are updated under
that specialist's name.


.. _OF:

Info Option -**OF** (-**OutputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

redirects output to a file instead of the
screen. The file format is compatible with **dsarch** input files.


.. _ON:

Info Option -**ON** (-**OrderNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a string of single-letter field codes
controlling the sort order of GET action results (:ref:`-GG <GG>`, :ref:`-GS <GS>`, :ref:`-GW <GW>`,
:ref:`-GH <GH>`, :ref:`-GQ <GQ>`). Uppercase means ascending; lowercase means descending.
When file records are modified via :ref:`-AS <AS>`, :ref:`-AW <AW>`, :ref:`-SS <SS>`, :ref:`-SW <SW>`, :ref:`-DL <DL>`, or
:ref:`-MV <MV>`, files in affected groups are reordered too.


.. _5.1_e11:

**EXAMPLE 11. To reorder an existing file list without other changes, use -SW with -ON:**

dsarch dNNNNNN :ref:`-SW <SW>` -ON OrderNameString [:ref:`-GI <GI>` GroupIndices]

Without group indices, reordering applies to all files in the
dataset.


.. _PO:

Info Option -**PO** (-**PatternOffset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

controls how **dsarch** matches file names
against group patterns to auto-assign group indices. A value >= 0
uses binary search (faster, for large sorted lists); -1 uses
linear search. Required when matching files already registered in
GDEXDB; defaults to -1 for new files.


.. _QS:

Info Option -**QS** (-**QsubOptions**) (Alias: -**PBSOptions**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

passes options to qsub
when running **dsarch** as a PBS batch job. Quote the value on the
command line, e.g., :ref:`-QS <QS>` '-l walltime=12:00:00'. With :ref:`-AL <AL>` N (N > 1),
'select=1:ncpus=N:mem=Ngb' is added to these options unless they
already request select, ncpus or mem.


.. _VS:

Info Option -**VS** (-**ValidSize**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the minimum acceptable file size (in bytes) for
archiving. Files smaller than this threshold are rejected.
Defaults to 100.


.. _WI:

Info Option -**WI** (-**WaitInternval**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

how long **dsarch** waits before rechecking
whether a background process slot has freed up (see :ref:`-AL <AL>`). Units:

.. list-table::
   :widths: auto
   :header-rows: 1
 S (seconds), M (minutes), H (hours), D (days) — e.g., '-WI 5M'. A bare number is treated as seconds.



| :ref:`Back to Top <section5.1>`
| :ref:`Back to Table of Contents <index>`
