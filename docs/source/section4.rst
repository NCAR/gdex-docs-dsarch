
.. _section4:

4 - MODE OPTIONS
=====================

Mode options adjust how an :ref:`Action option <section3>` behaves. They are all optional and
take no values — simply include the flag to activate the behavior.


.. _BG:

Mode Option -**BG** (-**BackGround**) (Alias: -**b**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

runs the action as a background process,
suppressing all screen output and error messages.


.. _CL:

Mode Option -**CL** (-**CleanLocal**) (Aliases: -**CleanLocFile**, -**CleanLocalFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

deletes local
source files once all have been successfully archived by :ref:`-AS <AS>` or :ref:`-AW <AW>`. Pair
with :ref:`-DD <DD>` (-DeleteDir) to also clean up any empty local directories.


.. _DX:

Mode Option -**DX** (-**DeleteXML**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

calls **dcm** to delete content metadata for the specified
Web files. With :ref:`-SW <SW>` (-SetWebFile), it explicitly removes metadata; with :ref:`-DL <DL>`
(-Delete) when Web files are specified, this happens automatically.


.. _EM:

Mode Option -**EM** (-**EmailNotice**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sends the executing specialist an email when an action
finishes or fails. Applies to :ref:`-AS <AS>`, :ref:`-AW <AW>`, :ref:`-AH <AH>`, :ref:`-AQ <AQ>`, :ref:`-SS <SS>`, :ref:`-SW <SW>`, :ref:`-SH <SH>`, :ref:`-SQ <SQ>`, :ref:`-RQ <RQ>`,
:ref:`-MV <MV>`, and :ref:`-DL <DL>`. The email includes a brief summary and any errors encountered.
Ignored when -d (:ref:`-BP <BP>`) is present.

Tip: when archiving many files, consolidate them into a single input file
and include :ref:`-EM <EM>` once — only one email is sent regardless of file count.


.. _FO:

Mode Option -**FO** (-**FormatOutput**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

aligns GET action output into fixed-width columns,
making results easier to read at a glance.


.. _GF:

Mode Option -**GF** (-**GrowingFile**) (Alias: -**GrowingDataFile**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

lifts the DOI/Version control lock on Web files so
that :ref:`-AW <AW>` (-ArchiveWebFile) can overwrite them. Use this when a file is
actively being appended to and must be updated in place. When `dsupdt <https://gdex-docs-dsupdt.readthedocs.io/en/latest/index.html>`_
drives :ref:`-AW <AW>`, growing files are detected and handled automatically.


.. _GX:

Mode Option -**GX** (-**GatherXML**) (Alias: -**Grid2XML**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

calls **gatherxml** to extract and
record content metadata for archived Web files. For :ref:`-MV <MV>` (-MoveFile), metadata
is transferred to the new file name automatically via **rcm** — :ref:`-GX <GX>` is not
needed for moves.


.. _GZ:

Mode Option -**GZ** (-**GMTZone**) (Aliases: -**GMT**, -**GreenwichZone**, -**UTC**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

records archiving
timestamps in GMT instead of local time.


.. _KM:

Mode Option -**KM** (-**KeepMetadata**) (Alias: -**KeepMeta**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

preserves the content metadata
record when a Web file is converted to a Saved file via :ref:`-MV <MV>` with :ref:`-TS <TS>`.


.. _KP:

Mode Option -**KP** (-**KeepPath**) (Alias: -**KeepLocalPath**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

preserves local file paths as-is
on the GDEX Server during :ref:`-AS <AS>`, :ref:`-AW <AW>`, and :ref:`-AH <AH>`. When :ref:`-KP <KP>` is active, :ref:`-SP <SP>` and :ref:`-WP <WP>`
are ignored. :ref:`-KP <KP>` is also ignored when destination file names are provided
explicitly via :ref:`-SF <SF>`, :ref:`-WF <WF>`, or :ref:`-HF <HF>`.


.. _MD:

Mode Option -**MD** (-**MyDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

bypasses the dataset ownership check, allowing any
specialist to modify records in GDEXDB for any dataset.


.. _NE:

Mode Option -**NE** (-**NoEmail**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

suppresses the automatic failure email notification.


.. _NT:

Mode Option -**NT** (-**NoTrim**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

skips stripping leading/trailing spaces and inline comments
from input values. Use this to speed up processing of large input files.


.. _NV:

Mode Option -**NV** (-**NewVersion**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

required to create a new DOI/Version control record
when using :ref:`-SV <SV>` (-SetVersion).


.. _OE:

Mode Option -**OE** (-**OverrideExist**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

allows an existing file on the GDEX Server to be
overwritten at the target path. Without this flag, archiving fails if the
destination already exists.


.. _PE:

Mode Option -**PE** (-**ShowPeriod**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

adds data period information (begin/end dates and times)
for the dataset and any specified groups to the output of :ref:`-GD <GD>` (-GetDataset).


.. _RA:

Mode Option -**RA** (-**RetryArchive**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

deprecated; has no effect and may be removed in a
future version.


.. _RD:

Mode Option -**RD** (-**RemoveDir**) (Aliases: -**RemoveDirectory**, -**RemoveEmptyDir**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

removes any
directories that become empty after file changes from :ref:`-DL <DL>`, :ref:`-SS <SS>`, or :ref:`-SW <SW>`.

To clean up empty directories without modifying files, run :ref:`-SS <SS>` or :ref:`-SW <SW>` with
:ref:`-RD <RD>` and no file names; **dsarch** will prune empty Web or Saved directories
for the specified dataset and groups.


.. _RG:

Mode Option -**RG** (-**RecursiveGroup**) (Alias: -**RepeatGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

descends into subgroups
recursively when used with :ref:`-GG <GG>`, :ref:`-GS <GS>`, or :ref:`-GW <GW>`, gathering all nested records.
A group index must be provided via :ref:`-GI <GI>` for this to take effect.


.. _RN:

Mode Option -**RN** (-**RelativeName**) (Aliases: -**RelativePathName**, -**RelativeFileName**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

returns file names as relative paths (relative to the
dataset or group's Saved or Web path) in the output of :ref:`-GS <GS>` and :ref:`-GW <GW>`.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

sets display order indices to match
the order files are listed when passed to :ref:`-SS <SS>`, :ref:`-SW <SW>`, :ref:`-SH <SH>`, or :ref:`-SQ <SQ>`. To set
explicit indices instead, use :ref:`-DO <DO>` (-DisplayOrder).

For sorting files by field values across an entire dataset or individual
groups, use :ref:`-ON <ON>` (-OrderNames).


.. _RS:

Mode Option -**RS** (-**GXRSOptions**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

passes the R and S flags to **gatherxml** to speed up
metadata evaluation. Use alongside :ref:`-GX <GX>` (-GatherXML).


.. _RT:

Mode Option -**RT** (-**ResetTIndex**) (Alias: -**ResetTopGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

recalculates and resets the
top-level group index stored in Saved or Web file records for the dataset
and any specified groups.


.. _SC:

Mode Option -**SC** (-**SetChecksum**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

calculates MD5 checksums for data files on the GDEX
Server and stores them in GDEXDB for integrity verification.


.. _TO:

Mode Option -**TO** (-**TarOnly**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

builds the Quasar tar file locally without uploading it
to the Globus Quasar Server. Useful for testing. Used with :ref:`-AQ <AQ>`.


.. _TS:

Mode Option -**TS** (-**ToSaved**) (Aliases: -**ToSavedFile**, -**MovedToSaved**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

used with :ref:`-MV <MV>` (-MoveFile)
to move Web files to Saved files.


.. _TT:

Mode Option -**TT** (-**TotalSummary**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

appends file count and size totals to the output
of :ref:`-GS <GS>` (-GetSavedFile) and :ref:`-GW <GW>` (-GetWebFile).


.. _TW:

Mode Option -**TW** (-**ToWeb**) (Aliases: -**ToWebFile**, -**MovedToWeb**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

used with :ref:`-MV <MV>` (-MoveFile)
to move Saved files to Web files.


.. _UZ:

Mode Option -**UZ** (-**UnzipData**) (Aliases: -**Uncompress**, -**UncompressData**, -**Unzip**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

decompresses files during
archiving. The tool is selected by extension: 'gunzip' for '.gz', 'uncompress'
for '.Z', 'unzip' for '.zip', and 'bunzip' for '.bz2'.


.. _WC:

Mode Option -**WC** (-**WithChecksum**) (Aliases: -**ValidateChecksum**, -**WithMD5**, -**ValidateMD5**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

adds MD5 checksum verification on top of size checks
when validating data files on the GDEX Server.


.. _WM:

Mode Option -**WM** (-**WithMetadata**) (Alias: -**WithMeta**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

triggers a fresh **gatherxml** run at the dataset or
group level when used with :ref:`-SD <SD>` (-SetDataset) or :ref:`-SG <SG>` (-SetGroup).


.. _WN:

Mode Option -**WN** (-**WithFileNumber**) (Alias: -**WithNumber**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

recomputes and updates Saved/Web file counts for the
dataset and any specified groups. With :ref:`-GD <GD>` (-GetDataset), the counts are
calculated on the fly and included in the output.


.. _XC:

Mode Option -**XC** (-**CrossCopy**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

used with :ref:`-AW <AW>` or :ref:`-AS <AS>` to fill gaps in storage: copies
files from Glade disk to Object Store (or vice versa) wherever copies are
missing.


.. _XM:

Mode Option -**XM** (-**CrossMove**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

like :ref:`-XC <XC>` but moves instead of copying — the original
file is deleted once the destination copy is confirmed.


.. _ZD:

Mode Option -**ZD** (-**ZipData**) (Aliases: -**Compress**, -**CompressData**, -**Zip**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

compresses files during :ref:`-AS <AS>` or
:ref:`-AW <AW>`. The compression tool is selected by the format given via :ref:`-AF <AF>`: 'gzip' for
'GZ', 'compress' for 'Z', 'zip' for 'ZIP', 'bzip' for 'BZ2'. Files already
in the target format are skipped. Files compressed in a different format are
uncompressed first (using the tool matched by extension: '.gz', '.Z', '.zip',
or '.bz2') before compressed again.



:ref:`Back to Top <section4>`
:ref:`Back to Table of Contents <index>`

