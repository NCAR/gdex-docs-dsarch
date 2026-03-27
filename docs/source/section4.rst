
.. _section4:

4 - MODE OPTIONS
=====================

Mode options adjust how an `Action <section3>`_ option behaves. They are all optional and
take no values — simply include the flag to activate the behavior.


.. _BG:

Mode Option -**BG** (-**BackGround**) (Alias: -**b**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

runs the action as a background process,
  suppressing all screen output and error messages.


.. _CL:

Mode Option -**CL** (-**CleanLocal**) (Aliases: -**CleanLocFile**, -**CleanLocalFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

deletes local
  source files once all have been successfully archived by -`AS <section3.4.9_>`_ or -`AW <section3.4.10_>`_. Pair
  with -`DD <section5.1_>`_ (-DeleteDir) to also clean up any empty local directories.


.. _DX:

Mode Option -**DX** (-**DeleteXML**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

calls **dcm** to delete content metadata for the specified
  Web files. With -`SW <section3.4.3_>`_ (-SetWebFile), it explicitly removes metadata; with -`DL <section3.4.15_>`_
  (-Delete) when Web files are specified, this happens automatically.


.. _EM:

Mode Option -**EM** (-**EmailNotice**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

sends the executing specialist an email when an action
  finishes or fails. Applies to -`AS <section3.4.9_>`_, -`AW <section3.4.10_>`_, -`AH <section3.4.11_>`_, -`AQ <section3.4.12_>`_, -`SS <section3.4.1_>`_, -`SW <section3.4.3_>`_, -`SH <section3.4.5_>`_, -`SQ <section3.4.7_>`_, -`RQ <section3.4.13_>`_,
  -`MV <section3.4.14_>`_, and -`DL <section3.4.15_>`_. The email includes a brief summary and any errors encountered.
  Ignored when -d (-`BP <section5.2_>`_) is present.

  Tip: when archiving many files, consolidate them into a single input file
  and include -`EM`_ once — only one email is sent regardless of file count.


.. _FO:

Mode Option -**FO** (-**FormatOutput**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

aligns GET action output into fixed-width columns,
  making results easier to read at a glance.


.. _GF:

Mode Option -**GF** (-**GrowingFile**) (Alias: -**GrowingDataFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

lifts the DOI/Version control lock on Web files so
  that -`AW <section3.4.10_>`_ (-ArchiveWebFile) can overwrite them. Use this when a file is
  actively being appended to and must be updated in place. When `dsupdt <https://gdex-docs-dsupdt.readthedocs.io/en/latest/index.html>`_
  drives -`AW <section3.4.10_>`_, growing files are detected and handled automatically.


.. _GX:

Mode Option -**GX** (-**GatherXML**) (Alias: -**Grid2XML**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

calls **gatherxml** to extract and
  record content metadata for archived Web files. For -`MV <section3.4.14_>`_ (-MoveFile), metadata
  is transferred to the new file name automatically via **rcm** — -`GX`_ is not
  needed for moves.


.. _GZ:

Mode Option -**GZ** (-**GMTZone**) (Aliases: -**GMT**, -**GreenwichZone**, -**UTC**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

records archiving
  timestamps in GMT instead of local time.


.. _KM:

Mode Option -**KM** (-**KeepMetadata**) (Alias: -**KeepMeta**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

preserves the content metadata
  record when a Web file is converted to a Saved file via -`MV <section3.4.14_>`_ with -`TS`_.


.. _KP:

Mode Option -**KP** (-**KeepPath**) (Alias: -**KeepLocalPath**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

preserves local file paths as-is
  on the GDEX Server during -`AS <section3.4.9_>`_, -`AW <section3.4.10_>`_, and -`AH <section3.4.11_>`_. When -`KP`_ is active, -`SP <section5.2_>`_ and -`WP <section5.2_>`_
  are ignored. -`KP`_ is also ignored when destination file names are provided
  explicitly via -`SF <section5.2_>`_, -`WF <section5.2_>`_, or -`HF <section5.2_>`_.


.. _MD:

Mode Option -**MD** (-**MyDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

bypasses the dataset ownership check, allowing any
  specialist to modify records in GDEXDB for any dataset.


.. _NE:

Mode Option -**NE** (-**NoEmail**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

suppresses the automatic failure email notification.


.. _NT:

Mode Option -**NT** (-**NoTrim**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

skips stripping leading/trailing spaces and inline comments
  from input values. Use this to speed up processing of large input files.


.. _NV:

Mode Option -**NV** (-**NewVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

required to create a new DOI/Version control record
  when using -`SV <section3.2.1_>`_ (-SetVersion).


.. _OE:

Mode Option -**OE** (-**OverrideExist**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

allows an existing file on the GDEX Server to be
  overwritten at the target path. Without this flag, archiving fails if the
  destination already exists.


.. _PE:

Mode Option -**PE** (-**ShowPeriod**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

adds data period information (begin/end dates and times)
  for the dataset and any specified groups to the output of -`GD <section3.1.2_>`_ (-GetDataset).


.. _RA:

Mode Option -**RA** (-**RetryArchive**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

deprecated; has no effect and may be removed in a
  future version.


.. _RD:

Mode Option -**RD** (-**RemoveDir**) (Aliases: -**RemoveDirectory**, -**RemoveEmptyDir**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

removes any
  directories that become empty after file changes from -`DL <section3.4.15_>`_, -`SS <section3.4.1_>`_, or -`SW <section3.4.3_>`_.

  To clean up empty directories without modifying files, run -`SS <section3.4.1_>`_ or -`SW <section3.4.3_>`_ with
  -`RD`_ and no file names; **dsarch** will prune empty Web or Saved directories
  for the specified dataset and groups.


.. _RG:

Mode Option -**RG** (-**RecursiveGroup**) (Alias: -**RepeatGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

descends into subgroups
  recursively when used with -`GG <section3.3.2_>`_, -`GS <section3.4.2_>`_, or -`GW <section3.4.4_>`_, gathering all nested records.
  A group index must be provided via -`GI <section5.2_>`_ for this to take effect.


.. _RN:

Mode Option -**RN** (-**RelativeName**) (Aliases: -**RelativePathName**, -**RelativeFileName**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

returns file names as relative paths (relative to the
  dataset or group's Saved or Web path) in the output of -`GS <section3.4.2_>`_ and -`GW <section3.4.4_>`_.


.. _RO:

Mode Option -**RO** (-**ResetOrder**) (Alias: -**Reorder**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

sets display order indices to match
  the order files are listed when passed to -`SS <section3.4.1_>`_, -`SW <section3.4.3_>`_, -`SH <section3.4.5_>`_, or -`SQ <section3.4.7_>`_. To set
  explicit indices instead, use -`DO <section5.2_>`_ (-DisplayOrder).

  For sorting files by field values across an entire dataset or individual
  groups, use -`ON <section5.1_>`_ (-OrderNames).


.. _RS:

Mode Option -**RS** (-**GXRSOptions**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

passes the R and S flags to **gatherxml** to speed up
  metadata evaluation. Use alongside -`GX`_ (-GatherXML).


.. _RT:

Mode Option -**RT** (-**ResetTIndex**) (Alias: -**ResetTopGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

recalculates and resets the
  top-level group index stored in Saved or Web file records for the dataset
  and any specified groups.


.. _SC:

Mode Option -**SC** (-**SetChecksum**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

calculates MD5 checksums for data files on the GDEX
  Server and stores them in GDEXDB for integrity verification.


.. _TO:

Mode Option -**TO** (-**TarOnly**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

builds the Quasar tar file locally without uploading it
  to the Globus Quasar Server. Useful for testing. Used with -`AQ <section3.4.12_>`_.


.. _TS:

Mode Option -**TS** (-**ToSaved**) (Aliases: -**ToSavedFile**, -**MovedToSaved**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

used with -`MV <section3.4.14_>`_ (-MoveFile)
  to move Web files to Saved files.


.. _TT:

Mode Option -**TT** (-**TotalSummary**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

appends file count and size totals to the output
  of -`GS <section3.4.2_>`_ (-GetSavedFile) and -`GW <section3.4.4_>`_ (-GetWebFile).


.. _TW:

Mode Option -**TW** (-**ToWeb**) (Aliases: -**ToWebFile**, -**MovedToWeb**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

used with -`MV <section3.4.14_>`_ (-MoveFile)
  to move Saved files to Web files.


.. _UZ:

Mode Option -**UZ** (-**UnzipData**) (Aliases: -**Uncompress**, -**UncompressData**, -**Unzip**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

decompresses files during
  archiving. The tool is selected by extension: 'gunzip' for '.gz', 'uncompress'
  for '.Z', 'unzip' for '.zip', and 'bunzip' for '.bz2'.


.. _WC:

Mode Option -**WC** (-**WithChecksum**) (Aliases: -**ValidateChecksum**, -**WithMD5**, -**ValidateMD5**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

adds MD5 checksum verification on top of size checks
  when validating data files on the GDEX Server.


.. _WM:

Mode Option -**WM** (-**WithMetadata**) (Alias: -**WithMeta**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

triggers a fresh **gatherxml** run at the dataset or
  group level when used with -`SD <section3.1.1_>`_ (-SetDataset) or -`SG <section3.3.1_>`_ (-SetGroup).


.. _WN:

Mode Option -**WN** (-**WithFileNumber**) (Alias: -**WithNumber**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

recomputes and updates Saved/Web file counts for the
  dataset and any specified groups. With -`GD <section3.1.2_>`_ (-GetDataset), the counts are
  calculated on the fly and included in the output.


.. _XC:

Mode Option -**XC** (-**CrossCopy**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

used with -`AW <section3.4.10_>`_ or -`AS <section3.4.9_>`_ to fill gaps in storage: copies
  files from Glade disk to Object Store (or vice versa) wherever copies are
  missing.


.. _XM:

Mode Option -**XM** (-**CrossMove**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

like -`XC`_ but moves instead of copying — the original
  file is deleted once the destination copy is confirmed.


.. _ZD:

Mode Option -**ZD** (-**ZipData**) (Aliases: -**Compress**, -**CompressData**, -**Zip**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

compresses files during -`AS <section3.4.9_>`_ or
  -`AW <section3.4.10_>`_. The compression tool is selected by the format given via -`AF <section5.2_>`_: 'gzip' for
  'GZ', 'compress' for 'Z', 'zip' for 'ZIP', 'bzip' for 'BZ2'. Files already
  in the target format are skipped. Files compressed in a different format are
  decompressed first (using the tool matched by extension: '.gz', '.Z', '.zip',
  or '.bz2') before recompressing.




:ref:`Back to Top <index>`
