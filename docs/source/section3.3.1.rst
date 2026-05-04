
.. _section3.3.1:

3.3.1 - Set Group Information
=================================


.. _SG:

Action Option -**SG** (-**SetGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates new or updates existing group records in
GDEXDB for the specified dataset. Multiple records can be processed
in one run.

| **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN [-](SG|SetGroup) [:ref:`Mode Options <mode3.3.1>`]
|           [:ref:`-(GI|GroupIndex) <GI>` GroupIndices]
|           [:ref:`-(GN|GroupName) <GN>` GroupNames]
|           [:ref:`-(PI|ParentIndex) <PI>` ParentGroupIndices]
|           [:ref:`-(TI|Title) <TI>` GroupTitles]
|           [:ref:`-(GT|GroupType) <GT>` GroupTypes]
|           [:ref:`-(GP|GroupPattern) <GP>` FileNamePatterns]
|           [:ref:`-(BF|BackupFlag) <BF>` QuasarBackupFlags]
|           [:ref:`-(DA|AccessFlag) <DA>` DataAccessFlags]
|           [:ref:`-(SP|SavedPath) <SP>` SavedFilePaths]
|           [:ref:`-(WP|WebPath) <WP>` WebFilePaths]
|           [:ref:`-(ML|MetaLink) <ML>` MetadataLinks]
|           [:ref:`-(NW|NoteWeb) <NW>` WebNotes]
|           [:ref:`-(NI|NoteInternal) <NI>` InternalNotes]
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(RT|ResetTGroup) <RT>`
     - resets the top group index for Saved/Web file records in the affected group
   * - :ref:`-(WM|WithMetadata) <WM>`
     - re-gathers Web file content metadata at the group level
   * - :ref:`-(WN|WithFileNumber) <WN>`
     - re-evaluates and resets Saved/Web file counts for the affected groups

If the group index already exists in GDEXDB, the record is updated;
otherwise a new group is created. New groups require a unique index.

To create a subgroup, set a parent index via :ref:`-PI <PI>` (-ParentIndex).
Groups can be nested to any depth. By default, three levels are shown
on group list webpages; adjust this with :ref:`-GL <GL>` (-GroupLevel) via :ref:`-SD <SD>`
(-SetDataset).

Changing a group's type from P (public) to I (internal) automatically
marks all its subgroups and associated Saved/Web files as internal too.


.. _3.3.1_e6:

**EXAMPLE 6. To set multiple group records for d744004 using an input file:**

| **dsarch** :ref:`SG <SG>` :ref:`-IF <IF>` d744004.grp

Content of input file d744004.grp:

.. code-block:: none

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



| :ref:`Back to Top <section3.3.1>`
| :ref:`Back to Table of Contents <index>`
