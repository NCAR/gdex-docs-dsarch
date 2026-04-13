
.. _section5.2:

5.2 - Multi-Value Info Options
=================================

A multi-value Info option accepts a list of one or more values. Supplying
zero values causes an error.


.. _AF:

Info Option -**AF** (-**ArchiveFormat**) (Aliases: -**FileFormat**, -**ExternalFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

describes
how a data file has been packaged or compressed. Recognized values:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - 'BI'
     - binary (COS) blocked
   * - 'C1' or 'CH'
     - ASCII/character blocked
   * - 'TAR'
     - tarred
   * - 'Z'
     - compressed
   * - 'GZ'
     - gzipped
   * - 'BZ2'
     - bzip2-compressed

Combine values in processing order, e.g., 'C1.TAR.GZ' = COS ASCII blocked,
then tarred, then gzipped. Maximum total length is 20 characters.


.. _BD:

Info Option -**BD** (-**BeginDate**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the earliest date covered by the data, for a group,
the whole dataset, or a version control record.


.. _BF:

Info Option -**BF** (-**BackupFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

controls whether and how a dataset or group is backed
up to Quasar. Values:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - 'N'
     - no auto-backup (dataset default)
   * - 'P'
     - inherit the setting from the parent (group default; index 0 inherits from the dataset)
   * - 'B'
     - back up files only
   * - 'D'
     - back up files and create a disaster recovery copy


.. _BP:

Info Option -**BP** (-**BatchProcess**) (Aliases: -**d**, -**DelayedMode**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

defers execution: the
command is written to GDEXDB and run later by the `dscheck <https://gdex-docs-dscheck.readthedocs.io>`_ daemon. One
or more host names may follow :ref:`-BP <BP>` to target or exclude specific hosts
(e.g., '-d PBS' to use PBS batch hosts). An optional retry limit (1-99)
can also be specified, e.g., '-d 5'; defaults to 2. Archive actions
(:ref:`-AS <AS>`, :ref:`-AW <AW>`, :ref:`-AH <AH>`, :ref:`-AQ <AQ>`) retry automatically after storage system outage.


.. _BS:

Info Option -**BS** (-**BackStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the current Quasar backup state for a file:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - 'A'
     - archived to Quasar (complete)
   * - 'T'
     - tar file created, awaiting upload
   * - 'N'
     - record created, awaiting tar


.. _BT:

Info Option -**BT** (-**BeginTime**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the time component of the data start, for a group,
the whole dataset, or a version control record.


.. _DA:

Info Option -**DA** (-**DataAccess**) (Aliases: -**DataAccessflag**, -**FileListFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

controls which
file list views are displayed at the dataset and/or top group level:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - 'B'
     - both complete and faceted
   * - 'C'
     - complete list only (default)
   * - 'F'
     - faceted list only
   * - 'N'
     - none (no file list shown)


.. _DB:

Info Option -**DB** (-**Debug**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

enables debug logging. Up to 3 values may be given: debug
level (required), log file path, and log file name. The level can be a
single integer (e.g., 1000) or a range (e.g., 200-1000). Defaults: log
path '$DECSHOME/dssdb/log', file name 'mydss.dbg'.


.. _DE:

Info Option -**DE** (-**Description**) (Aliases: -**Desc**, -**Note**, -**FileDesc**, -**FileDescription**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a
free-text description for a data file or version record. Multi-line values
are supported in input files (:ref:`-IF <IF>`). Quote values containing spaces on the
command line. With version control actions (:ref:`-SV <SV>`), this becomes the version
note.


.. _DF:

Info Option -**DF** (-**DataFormat**) (Aliases: -**TF**, -**ContentFormat**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the
scientific format of the data content (e.g., NetCDF, IMMA, BINARY). A
dataset-level default can be set via :ref:`-SD <SD>` and is applied automatically when
no format is specified at archive time.


.. _DN:

Info Option -**DN** (-**DOINumber**) (Aliases: -**DOI**, -**DOIName**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the Digital Object Identifier
assigned to a dataset version, providing a stable, citable reference.


.. _DO:

Info Option -**DO** (-**DisplayOrder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

explicit display position indices for files within a
group or across the dataset. Overridden by :ref:`-RO <RO>` (-ResetOrder) when both are
present.


.. _ED:

Info Option -**ED** (-**EndDate**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the latest date covered by the data, for a group,
the whole dataset, or a version control record.


.. _ET:

Info Option -**ET** (-**EndTime**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the time component of the data end, for a group,
the whole dataset, or a version control record.


.. _EV:

Info Option -**EV** (-**ExternalVersion**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the human-readable version label shown publicly
for a dataset (e.g., '2.0'). Empty by default.


.. _FD:

Info Option -**FD** (-**FileDate**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the calendar date a data file was last modified.


.. _FF:

Info Option -**FF** (-**FileFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

specifies whether an entry represents a regular file
('F') or a directory path ('P').


.. _FS:

Info Option -**FS** (-**FileStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the access level of a file: 'P' (public, visible to
all users) or 'I' (internal, visible to specialists only).


.. _FT:

Info Option -**FT** (-**FileTime**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the time of day a data file was last modified.


.. _GI:

Info Option -**GI** (-**GroupIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

assigns files to a specific group within a dataset.
Groups must be created first via :ref:`-SG <SG>` (-SetGroup). Use 1, 2, 3, ... for
specific groups; 0 means no group assignment (default).

When omitted for :ref:`-AS <AS>` or :ref:`-AW <AW>`, **dsarch** attempts to assign groups
automatically by matching file names against patterns stored in GDEXDB.


.. _GL:

Info Option -**GL** (-**GroupLevel**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the number of group nesting levels displayed on the
web interface. Defaults to 2. A value of -2 shows one level initially,
expanding to two when subgroups are present.


.. _GN:

Info Option -**GN** (-**GroupName**) (Alias: -**GroupID**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a short human-readable identifier for
a group (up to 20 characters). Set via :ref:`-SG <SG>` (-SetGroup). Names can be used
wherever group indices are accepted, and appear on file list webpages.


.. _GP:

Info Option -**GP** (-**GroupPattern**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

wildcard patterns that **dsarch** uses to automatically
assign files to the right group during archiving. Stored per group via :ref:`-SG <SG>`.


.. _GT:

Info Option -**GT** (-**GroupType**) (Alias: -**GroupDataType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the access level for a group:

.. list-table::
   :widths: auto
   :header-rows: 1
 'P' (public) or 'I' (internal). Changing from P to I recursively marks all nested subgroups and their Web files as internal.


.. _HF:

Info Option -**HF** (-**HelpFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the destination names for Help files on the GDEX Server.
Defaults to the local file names from :ref:`-LF <LF>` unless overridden explicitly.


.. _HT:

Info Option -**HT** (-**HelpFileType**) (Alias: -**HelpType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the category of a Help file:

.. list-table::
   :widths: auto
   :header-rows: 1
 'D' (Document) or 'S' (Software). One value applies to all files in the batch.


.. _ID:

Info Option -**ID** (-**InitialDate**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the original publication or release date of a Help,
Document, or Software file.


.. _IF:

Info Option -**IF** (-**InputFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

one or more input file names provided on the command
line. Each file name must start with the dataset number (format 'dNNNNNN.*')
and match the :ref:`-DS <DS>` value. This naming rule is a safeguard against accidentally
running an action on the wrong dataset.

Input file format rules:

* Lines beginning with '#' are comments and are ignored.
* Option names may be short, long, or alias forms.
* :ref:`Action <section3>`/Mode options: OptionName<!>  (marker changeable via -AO)
* Single-value assignments: OptionName<=>Value, one per line (delimiter changeable via -ES; default '<=>')
* Multi-value (tabular) assignments: a title row followed by data rows, with columns separated by '<:>' (changeable via -DV).
* Tabular data ends at EOF or when a new title line or single-value assignment is encountered.
* If the last column contains multi-line text, append the separator to every row (including the title line).


.. _IV:

Info Option -**IV** (-**InternalVersion**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a minor revision counter within the same DOI.
Increments when data are updated without changing the DOI itself. Starts
at 1 when a new DOI record is created.


.. _KV:

Info Option -**KV** (-**KeyValue**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

custom key/value metadata pairs for a dataset. Use :ref:`-SD <SD>`
to set them and :ref:`-GD <GD>` to view them. Keys: up to 40 characters; values: up to
128 characters.

Set a pair:

.. list-table::
   :widths: auto
   :header-rows: 1
 dsarch d540000 SD :ref:`-KV <KV>` 'test=>test it'

View a specific key:

.. list-table::
   :widths: auto
   :header-rows: 1
 dsarch d540000 GD :ref:`-KV <KV>` test

View all pairs:

.. list-table::
   :widths: auto
   :header-rows: 1
 dsarch d540000 GD :ref:`-KV <KV>` all


.. _LC:

Info Option -**LC** (-**Location**) (Alias: -**LocationFlag**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

where the file resides:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - 'C'
     - CGD data path
   * - 'G'
     - Glade Disk (NCAR HPC file system)
   * - 'O'
     - bOreas
   * - 'B'
     - both Glade and bOreas
   * - 'R'
     - remote URL (Help files only)

At the dataset level (as the online access location), only 'G' or 'O'
are valid.


.. _LF:

Info Option -**LF** (-**LocalFile**) (Aliases: -**LocFile**, -**SourceFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the local source files to
archive via :ref:`-AS <AS>`, :ref:`-AW <AW>`, or :ref:`-AH <AH>`. UNIX wildcards ('*', '?') are accepted on
the command line. Use absolute or relative paths for files outside the
current directory.


.. _MC:

Info Option -**MC** (-**MD5Checksum**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the MD5 checksum of a data file on the GDEX Server,
used for integrity verification.


.. _ML:

Info Option -**ML** (-**MetaLink**) (Alias: -**MetadataLink**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a URL pointing to the content
metadata page for a dataset, group, or file. Normally set automatically by
**gatherxml** when :ref:`-GX <GX>` is used. A custom value may be provided and will
take precedence over the auto-generated link.


.. _ND:

Info Option -**ND** (-**NoteDocument**) (Aliases: -**DocumentNote**, -**DescDocument**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a brief
description of the documentation available for a dataset.


.. _NI:

Info Option -**NI** (-**NoteInternal**) (Aliases: -**InternalNote**, -**DescInternal**, -**DI**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

an internal
note about a group's or dataset's data, visible to specialists only.


.. _NS:

Info Option -**NS** (-**NoteSoftware**) (Aliases: -**SoftwareNote**, -**DescSoftware**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a description of
any software tools or scripts associated with a dataset.


.. _NW:

Info Option -**NW** (-**NoteWeb**) (Aliases: -**WebNote**, -**DescWeb**, -**DW**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a public-facing description
of the web-accessible data for a group or the dataset as a whole.


.. _OB:

Info Option -**OB** (-**OrderBy**) (Alias: -**OrderByPattern**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a date/time pattern that guides
temporal sorting when combined with :ref:`-ON <ON>`. For example, 'YYYYmon' sorts by
4-digit year followed by 3-letter month abbreviation.


.. _OD:

Info Option -**OD** (-**OriginDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the dataset the files are being moved from when
using :ref:`-MV <MV>` (-MoveFile).


.. _OG:

Info Option -**OG** (-**OriginGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the existing group indices to be renumbered by
:ref:`-CG <CG>` (-ChangeGroup).


.. _OT:

Info Option -**OT** (-**OriginType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the source file type when converting between types
(e.g., Web to Saved) during a :ref:`-MV <MV>` (-MoveFile) operation.


.. _PI:

Info Option -**PI** (-**ParentIndex**) (Alias: -**ParentGroupIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the index of the parent
group for a subgroup. Groups can be nested to any depth.


.. _QF:

Info Option -**QF** (-**QuasarFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the name of the Quasar backup (tar) file, required
for :ref:`-AQ <AQ>` (-ArchiveQuasarFile).


.. _QT:

Info Option -**QT** (-**QuasarFileType**) (Aliases: -**QuasarType**, -**BackupType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the backup scope:

.. list-table::
   :widths: auto
   :header-rows: 1
 'B' (backup only) or 'D' (backup plus disaster recovery copy).


.. _RF:

Info Option -**RF** (-**OriginFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the source file names for :ref:`-MV <MV>` (-MoveFile) when they
differ from the destination names given via :ref:`-SF <SF>`, :ref:`-WF <WF>`, or :ref:`-HF <HF>`.


.. _SF:

Info Option -**SF** (-**SavedFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the destination names for Saved files on the GDEX Server.
For :ref:`-AS <AS>` (-ArchiveSavedFile), defaults to the local file names from :ref:`-LF <LF>`
unless specified explicitly.


.. _SP:

Info Option -**SP** (-**SavedPath**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the directory path for Saved files, relative to the
Saved data home directory. For :ref:`-AS <AS>`, the dataset or group's stored path is
used by default. For :ref:`-SG <SG>` and :ref:`-SD <SD>`, this value is written to GDEXDB.

Keeping Saved paths accurate is important: NCAR users browse data through
'gdexls' using these paths. Each top-level group should map to one directory,
with one subdirectory per subgroup level, mirroring the physical layout.


.. _SR:

Info Option -**SR** (-**Source**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the person, team, or organization that contributed or
produced a Help file.


.. _ST:

Info Option -**ST** (-**SavedFileType**) (Aliases: -**SavedType**, -**SavedArchiveType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the role of a
Saved file:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - 'P'
     - Primary (main dataset file)
   * - 'R'
     - Original (source/raw copy)
   * - 'W'
     - Work (working/intermediate file)
   * - 'S'
     - Scratch (temporary file)
   * - 'V'
     - Version-controlled (locked under DOI)

One value applies to all files in the batch.


.. _SZ:

Info Option -**SZ** (-**Size**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the file size in bytes. Measured automatically from local
files during archiving; provide explicitly to override.


.. _TG:

Info Option -**TG** (-**TopGroupIndex**) (Alias: -**TopGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the index of the outermost
(top-level) group that a Saved or Web file belongs to within a group
hierarchy.


.. _TI:

Info Option -**TI** (-**Title**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the display title for a dataset or group. Dataset titles
cannot be changed through **dsarch** — use the Metadata Editor instead.


.. _TL:

Info Option -**TL** (-**ThreddLink**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

a URL to the THREDDS Catalog page for a specific file.
Set to 'Y' to indicate that THREDDS Catalog information has been gathered.


.. _VI:

Info Option -**VI** (-**VersionIndex**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the numeric identifier of a specific DOI/Version
control record for a dataset.


.. _VT:

Info Option -**VT** (-**VersionStatus**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the life cycle state of a version control record:

.. list-table::
   :widths: auto
   :header-rows: 1
 'A' (Active), 'P' (Pending — no DOI yet), or 'H' (History — terminated).


.. _WF:

Info Option -**WF** (-**WebFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the destination names for Web files on the GDEX Server.
For :ref:`-AW <AW>` (-ArchiveWebFile), defaults to the local file names from :ref:`-LF <LF>`
unless specified explicitly.


.. _WH:

Info Option -**WH** (-**WebHome**) (Alias: -**WebDataHome**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

an alternative Web data home
directory for a dataset. Stored in GDEXDB via :ref:`-SD <SD>` (-SetDataset).


.. _WP:

Info Option -**WP** (-**WebPath**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the directory path for Web files, relative to the Web
data home directory. For :ref:`-AW <AW>`, the dataset or group's stored path is used
by default. For :ref:`-SG <SG>` and :ref:`-SD <SD>`, this value is written to GDEXDB.

Keeping Web paths accurate is important: NCAR users browse data through
'gdexls' using these paths. Each top-level group should map to one directory,
with one subdirectory per subgroup level, mirroring the physical layout.


.. _WT:

Info Option -**WT** (-**WebFileType**) (Aliases: -**WebType**, -**WebArchiveType**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the accessibility of
a Web file: 'D' (public data) or 'N' (NCAR internal data only). One value
applies to all files in the batch.


.. _WU:

Info Option -**WU** (-**WebURL**) (Aliases: -**URL**, -**WebAddress**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

the full URL of a Help file
hosted remotely (e.g., on GitHub). Use with :ref:`-SH <SH>` (-SetHelpFile) to register
the file in GDEXDB without a local copy on the GDEX Server.



| :ref:`Back to Top <section5.2>`
| :ref:`Back to Table of Contents <index>`
