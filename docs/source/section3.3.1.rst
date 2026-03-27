
.. _section3.3.1:

3.3.1 - Set Group Information
=====================


.. _SG:

Action Option -**SG** (-**SetGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates new or updates existing group records in GDEXDB
  for the specified dataset. Multiple records can be processed in one run.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](SG|SetGroup) [`Mode Options <mode_>`_]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|         [-(`GN|GroupName <section5.2_>`_) GroupNames]
|         [-(`PI|ParentIndex <section5.2_>`_) ParentGroupIndices]
|         [-(`TI|Title <section5.2_>`_) GroupTitles]
|         [-(`GT|GroupType <section5.2_>`_) GroupTypes]
|         [-(`GP|GroupPattern <section5.2_>`_) FileNamePatterns]
|         [-(`BF|BackupFlag <section5.2_>`_) QuasarBackupFlags]
|         [-(`DA|AccessFlag <section5.2_>`_) DataAccessFlags]
|         [-(`SP|SavedPath <section5.2_>`_) SavedFilePaths]
|         [-(`WP|WebPath <section5.2_>`_) WebFilePaths]
|         [-(`ML|MetaLink <section5.2_>`_) MetadataLinks]
|         [-(`NW|NoteWeb <section5.2_>`_) WebNotes]
|         [-(`NI|NoteInternal <section5.2_>`_) InternalNotes]
|         [-(`LN|LoginName <section5.1_>`_) LoginAccountName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`RT|ResetTGroup <section4_>`_)
     - resets the top group index for Saved/Web file records in the affected group
   * - -(`WM|WithMetadata <section4_>`_)
     - re-gathers Web file content metadata at the group level
   * - -(`WN|WithFileNumber <section4_>`_)
     - re-evaluates and resets Saved/Web file counts for the affected groups

  If the group index already exists in GDEXDB, the record is updated; otherwise
  a new group is created. New groups require a unique index.

  To create a subgroup, set a parent index via -`PI <section5.2_>`_ (-ParentIndex). Groups can
  be nested to any depth. By default, three levels are shown on group list
  webpages; adjust this with -`GL <section5.2_>`_ (-GroupLevel) via -`SD <section3.1.1_>`_ (-SetDataset).

  Changing a group's type from P (public) to I (internal) automatically marks
  all its subgroups and associated Saved/Web files as internal too.


.. _3.3.1_e6:

**EXAMPLE 6. To set multiple group records for d744004 using an input file:**

| **dsarch** `SG`_ -`IF <section5.2_>`_ d744004.grp

Content of input file d744004.grp:

Dataset<=>d744004
EndDate<=>2005-09-30
GroupIndex<:>Title<:>GroupPattern<:>DescWeb<:>
1<:>Blended Wind<:>.bln<:>
The 'bln' product is the blended wind field output.<:>
2<:>NCEP Re-analyses<:>.low<:>
The 'low' fields consist of the NCEP re-analyses splined
to the 0.5 x 0.5 degree grid (i.e. no QSCAT data blended).<:>
3<:>Superposition of QSCAT Observations<:>.sub<:>
The 'sub' product is output from an intermediate step in the blending process
that consists of the superposition of QSCAT observations on NCEP before
blending. This product is of no particular scientific value, but very useful
in identifying the satellite data swaths in each composite of 12-hours of
QSCAT observations.<:>




:ref:`Back to Top <index>`
