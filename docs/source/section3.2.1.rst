
.. _section3.2.1:

3.2.1 - Set Version Control
=====================


.. _SV:

Action Option -**SV** (-**SetVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

adds and modifies DOI/Version controls for a given dataset number.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](SV|SetVersion) [`Mode Options <#mode>`_]
|   [-(`VI|VersionIndex <section5.2.rst#VI>`_) VersionIndex]
|   [-(`IV|InternalVersion <section5.2.rst#IV>`_) InternalVersionIndex]
|   [-(`EV|ExternalVersion <section5.2.rst#EV>`_) AssignedVersionNumber]
|   [-(`DN|DOINumber <section5.2.rst#DN>`_) DOInumber]
|   [-(`VT|VersionStatus <section5.2.rst#VT>`_) VersionRecordStatus]
|   [-(`BD|BeginDate <section5.2.rst#BD>`_) VersionStartdate]
|   [-(`BT|BeginTime <section5.2.rst#BT>`_) VersionStartTime]
|   [-(`ED|EndDate <section5.2.rst#ED>`_) VersionEnddate]
|   [-(`ET|EndTime <section5.2.rst#ET>`_) VersionEndTime]
|   [-(`DE|Description <section5.2.rst#DE>`_) VersionNote]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for setting DOI/Version control action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skips trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`NV|NewVersion <section4.rst#NV>`_)
     - adds a new version control record into RDADB

  If a version index is given and it is in RDADB already, its record is modified.
  A new version control record is added if version control index is not given or it is
  0 and `Mode <section4.rst>`_ option -`NV <section4.rst#NV>`_ (-NewVersion) is present.

  When a version control record is first added into RDADB without DOI number specified,
  it is in status of Pending. It can only be changed to Active if a DOI number
  is provided. An active version control record is added with a new DOI number and a
  version control index is auto-generated.


.. _e3:

**EXAMPLE 3. **

Put Dataset D999009 Under Doi/Version Control

  dsarch d999009 SV -`NV <section4.rst#NV>`_ -DN DOINumber

  If the data of d999009 are updated mostly or completely to a newer version (set of
  files) a new DOI number is needed. You may execute the same **dsarch** command to
  add another new active version control record with a new DOI number. The previous
  version control record is changed automatically to status of History and its DOI number
  is superseded now by the current DOI number. Only one active version control record can
  exist for a give dataset.

  If the data of d999009 are modified minimally a new internal version index is needed
  with the same DOI number, you may execute the same **dsarch** command to add another
  new version control record with a new internal version index but the same existing DOI
  number. The previous version control record is also changed to status of History.

  One case of the minimal data change is to replace one or multiple erroneous Web
  files under version control. The files are first moved to different filenames
  via dsarch Action -`MV <section3.4.14.rst>`_. The file type is autmatically set to 'V' as Version
  controlled type. A new internal version can be optionally added at this time. Then
  new Web files are added as replacements.

  Usage Note: Various RDA use cases are described here. It is recommended that you review
  and know these use cases, so that the DOIs in the RDA are handled consistently.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
