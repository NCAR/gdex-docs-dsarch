
.. _section5.1:

5.1 - Single-Value Info Options
=====================

A single-value Info option accepts exactly one value. Providing no value or
more than one causes an error.


.. _AL:

Info Option -**AL** (-**AsyncLimit**) (Alias: -**AsynchronousLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

caps the number of
simultaneous background processes spawned for 'cp' and **gatherxml** calls.
Has no effect when running as a PBS batch job.


.. _AO:

Info Option -**AO** (-**ActionOption**) (Alias: -**ActOption**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the token that marks :ref:`Action <section3>` and
:ref:`Mode options <section4>` in input files. Defaults to '<!>'. Change this if your input
data contains the default token.


.. _BL:

Info Option -**BL** (-**ButtonLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the minimum file count at which download script buttons
appear on file list web pages. Defaults to 2.


.. _DD:

Info Option -**DD** (-**DeleteDir**) (Aliases: -**DeleteDirLevel**, -**DeleteEmptyDir**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

how many levels
of empty parent directories to prune after files are deleted or moved.
Applies to -:ref:`DL <DL>`, -:ref:`MV <MV>`, and -:ref:`CL <CL>` (when used with -:ref:`AS <AS>` or -:ref:`AW <AW>`).


.. _DS:

Info Option -**DS** (-**Dataset**) (Aliases: -**Dsid**, -**DatasetID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the target dataset ID (format: [a-z]NNNNNN). Required
by almost all actions.


.. _DV:

Info Option -**DV** (-**Divider**) (Aliases: -**Delimiter**, -**Separater**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the column separator used
for multi-value Info options in input files. Defaults to '<:>'.


.. _ES:

Info Option -**ES** (-**EqualSign**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the token used to assign a value to an option in input
files (e.g., 'Dataset<=>d123456'). Defaults to '<=>'.


.. _FL:

Info Option -**FL** (-**FileLimit**) (Alias: -**FileCountLimit**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file count threshold for
static file list pages. Groups whose combined count falls below this limit
are shown together on one page; a group whose count exceeds it is split
across multiple sub-pages. Defaults to 2000.


.. _FN:

Info Option -**FN** (-**FieldNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a compact string of single-letter codes that selects
which fields to include in GET action output. Default codes are listed in
each action's section; use ALL to retrieve every available field.


.. _LD:

Info Option -**LD** (-**LocalDirectory**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a local directory to source files from. All files
within it and any sub-directories are collected recursively.


.. _LL:

Info Option -**LL** (-**LocalFileList**) (Alias: -**LocalList**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a plain-text file listing local file names to
process, one name per line.


.. _LN:

Info Option -**LN** (-**LoginName**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the login name to attribute the action to. Defaults to
the current user. Use this when running on behalf of another specialist or
from an automated process (daemon or cron job). Use with care — it affects
which records are updated under that specialist's name.


.. _OF:

Info Option -**OF** (-**OutputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

redirects output to a file instead of the screen.
The file format is compatible with **dsarch** input files.


.. _ON:

Info Option -**ON** (-**OrderNames**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a string of single-letter field codes controlling the
sort order of GET action results (-:ref:`GG <GG>`, -:ref:`GS <GS>`, -:ref:`GW <GW>`, -:ref:`GH <GH>`, -:ref:`GQ <GQ>`). Uppercase means
ascending; lowercase means descending. When file records are modified via
-:ref:`AS <AS>`, -:ref:`AW <AW>`, -:ref:`SS <SS>`, -:ref:`SW <SW>`, -:ref:`DL <DL>`, or -:ref:`MV <MV>`, files in affected groups are reordered too.

To reorder an existing file list without other changes, use -:ref:`SW <SW>` with -:ref:`ON <ON>`:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - dsarch dNNNNNN -:ref:`SW <SW>` -ON OrderNameString [-:ref:`GI <GI>` GroupIndices]

Without group indices, reordering applies to all files in the dataset.


.. _PO:

Info Option -**PO** (-**PatternOffset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

controls how **dsarch** matches file names against
group patterns to auto-assign group indices. A value >= 0 uses binary
search (faster, for large sorted lists); -1 uses linear search. Required
when matching files already registered in GDEXDB; defaults to -1 for new
files.


.. _QS:

Info Option -**QS** (-**QsubOptions**) (Alias: -**PBSOptions**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

passes options to qsub when
running **dsarch** as a PBS batch job. Quote the value on the command line,
e.g., -:ref:`QS <QS>` '-l walltime=12:00:00'.


.. _UD:

Info Option -**UD** (-**UseDSARCH**) (Alias: -**UseRDADB**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the gating flag that controls
**dsarch** access to a dataset. Set via -:ref:`SD <SD>` (-SetDataset). Values:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - 'N'
     - disabled (default; blocks all **dsarch** writes)
   * - 'Y'
     - enabled for modification
   * - 'I'
     - enabled for internal users only
   * - 'P'
     - enabled and file lists are published publicly
   * - 'W'
     - file list publication only Any value except 'N' must be set before **dsarch** can write to GDEXDB.


.. _VS:

Info Option -**VS** (-**ValidSize**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the minimum acceptable file size (in bytes) for
archiving. Files smaller than this threshold are rejected. Defaults to 100.


.. _WI:

Info Option -**WI** (-**WaitInternval**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

how long **dsarch** waits before rechecking whether a
background process slot has freed up (see -:ref:`AL <AL>`). Units: S (seconds),
M (minutes), H (hours), D (days) — e.g., '-:ref:`WI <WI>` 5M'. A bare number is
treated as seconds.




:ref:`Back to Top <index>`
