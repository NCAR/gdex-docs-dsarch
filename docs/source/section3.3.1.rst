
.. _section3.3.1:

3.3.1 - Set Group Information
=====================


.. _SG:

Action Option -**SG** (-**SetGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates and modifies group information into RDADB for a
  given dataset number. One or multiple groups can be processed each time.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](SG|SetGroup) [`Mode Options <#mode>`_]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`GN|GroupName <section5.2.rst#GN>`_) GroupNames]
|   [-(`PI|ParentIndex <section5.2.rst#PI>`_) ParentGroupIndices]
|   [-(`TI|Title <section5.2.rst#TI>`_) GroupTitles]
|   [-(`GT|GroupType <section5.2.rst#GT>`_) GroupTypes]
|   [-(`GP|GroupPattern <section5.2.rst#GP>`_) FileNamePatterns]
|   [-(`BF|BackupFlag <section5.2.rst#BF>`_) QuasarBackupFlags]
|   [-(`DA|AccessFlag <section5.2.rst#DA>`_) DataAccessFlags]
|   [-(`SP|SavedPath <section5.2.rst#SP>`_) SavedFilePaths]
|   [-(`WP|WebPath <section5.2.rst#WP>`_) WebFilePaths]
|   [-(`ML|MetaLink <section5.2.rst#ML>`_) MetadataLinks]
|   [-(`NW|NoteWeb <section5.2.rst#NW>`_) WebNotes]
|   [-(`NI|NoteInternal <section5.2.rst#NI>`_) InternalNotes]
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for setting group action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`RT|ResetTGroup <section4.rst#RT>`_)
     - reset top group index for all the Saved/Web file records in a group
   * - -(`WM|WithMetadata <section4.rst#WM>`_)
     - re-gathers Web file content metadata at the group level
   * - -(`WN|WithFileNumber <section4.rst#WN>`_)
     - re-evaluates and resets Saved/Web file counts for the affected groups

  If a group index per option -`GI <section5.2.rst#GI>`_ (-GroupIndex) exists in RDADB already for the
  specified dataset, group record is modified; otherwise, a new group record is
  added. For a new group record, a unique group index number must be provided.

  A tree structure of groups can set by using subgroups. A subgroups is created
  if its parent group index is identified per options -`PI <section5.2.rst#PI>`_ (-ParentIndex).
  Theoretically there is no limits how many levels of subgroups can be set.
  As default, three subgroup levels are displayed on group list webpages; but it
  can be reset to any number by option -`GL <section5.2.rst#GL>`_ (-GroupLevel) per action -`SD <section3.1.1.rst>`_
  (-SetDataset).

  If a group type is changed from P to I, all its subgroups are set to I
  recursively, and all Saved/Web Files under the group or its subgroups are
  also set to I.


.. _e6:

**EXAMPLE 6. **

Set Multiple Group Information Of D744004 Via Input File
  'd744004.grp'

| **dsarch** `SG <#SG>`_ -`IF <section5.2.rst#IF>`_ d744004.grp

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



.. raw:: html

   <br>

:ref:`Back to Top <index>`
