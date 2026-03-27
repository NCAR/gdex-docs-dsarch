
.. _section3.2.1:

3.2.1 - Set Version Control
=====================


.. _SV:

Action Option -**SV** (-**SetVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates a new or updates an existing DOI/Version control
  record for the specified dataset.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](SV|SetVersion) [`Mode Options <mode_>`_]
|         [-(`VI|VersionIndex <section5.2_>`_) VersionIndex]
|         [-(`IV|InternalVersion <section5.2_>`_) InternalVersionIndex]
|         [-(`EV|ExternalVersion <section5.2_>`_) AssignedVersionNumber]
|         [-(`DN|DOINumber <section5.2_>`_) DOInumber]
|         [-(`VT|VersionStatus <section5.2_>`_) VersionRecordStatus]
|         [-(`BD|BeginDate <section5.2_>`_) VersionStartdate]
|         [-(`BT|BeginTime <section5.2_>`_) VersionStartTime]
|         [-(`ED|EndDate <section5.2_>`_) VersionEnddate]
|         [-(`ET|EndTime <section5.2_>`_) VersionEndTime]
|         [-(`DE|Description <section5.2_>`_) VersionNote]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4_>`_)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - -(`NT|NoTrim <section4_>`_)
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - -(`NV|NewVersion <section4_>`_)
     - adds a new version control record to GDEXDB

  If a version index is provided and already exists in GDEXDB, the record is
  modified. A new record is created when no index is given (or it is 0) and `Mode <section4>`_
  option -`NV <section4_>`_ (-NewVersion) is present.

  A newly created record with no DOI number is in Pending status and can only
  transition to Active once a DOI number is supplied. When an active record is
  created with a new DOI number, the version control index is auto-generated.


.. _3.2.1_e3:

**EXAMPLE 3. To place d999009 under DOI/Version control:**

  dsarch d999009 SV -`NV <section4_>`_ -DN DOINumber

  If the data of d999009 are substantially updated to a new version, run the
  same command with a new DOI number. The previous active record is automatically
  moved to History status and its DOI is superseded. Only one active version
  control record may exist per dataset.

  For minimal data changes under the same DOI, run the same command with the
  existing DOI number to create a new internal version index. The previous
  record is again moved to History.

  One common minimal-change case is replacing erroneous Web files. First, move
  the affected files to different names using Action -`MV <section3.4.14_>`_ (their type is
  automatically set to 'V' for Version-controlled). Optionally create a new
  internal version at this point, then archive the replacement Web files.

  Note: Various GDEX use cases are outlined above. Review them so that DOIs in
  the GDEX are handled consistently.




:ref:`Back to Top <index>`
