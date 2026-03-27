
.. _section3.2.1:

3.2.1 - Set Version Control
=====================


.. _SV:

Action Option -**SV** (-**SetVersion**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

creates a new or updates an existing DOI/Version control
record for the specified dataset.

|  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN [-](SV|SetVersion) [:ref:`Mode Options <mode3.2.1>`]
|             [:ref:`-(VI|VersionIndex) <VI>` VersionIndex]
|             [:ref:`-(IV|InternalVersion) <IV>` InternalVersionIndex]
|             [:ref:`-(EV|ExternalVersion) <EV>` AssignedVersionNumber]
|             [:ref:`-(DN|DOINumber) <DN>` DOInumber]
|             [:ref:`-(VT|VersionStatus) <VT>` VersionRecordStatus]
|             [:ref:`-(BD|BeginDate) <BD>` VersionStartdate]
|             [:ref:`-(BT|BeginTime) <BT>` VersionStartTime]
|             [:ref:`-(ED|EndDate) <ED>` VersionEnddate]
|             [:ref:`-(ET|EndTime) <ET>` VersionEndTime]
|             [:ref:`-(DE|Description) <DE>` VersionNote]

.. _mode3.2.1:

:ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(NV|NewVersion) <NV>`
     - adds a new version control record to GDEXDB

If a version index is provided and already exists in GDEXDB, the record is
modified. A new record is created when no index is given (or it is 0) and :ref:`Mode <section4>`
option -:ref:`NV <NV>` (-NewVersion) is present.

A newly created record with no DOI number is in Pending status and can only
transition to Active once a DOI number is supplied. When an active record is
created with a new DOI number, the version control index is auto-generated.


.. _3.2.1_e3:

**EXAMPLE 3. To place d999009 under DOI/Version control:**

|  **dsarch** d999009 :ref:`SV <SV>` -:ref:`NV <NV>` -:ref:`DN <DN>` DOINumber

If the data of d999009 are substantially updated to a new version, run the
same command with a new DOI number. The previous active record is automatically
moved to History status and its DOI is superseded. Only one active version
control record may exist per dataset.

For minimal data changes under the same DOI, run the same command with the
existing DOI number to create a new internal version index. The previous
record is again moved to History.

One common minimal-change case is replacing erroneous Web files. First, move
the affected files to different names using Action -:ref:`MV <MV>` (their type is
automatically set to 'V' for Version-controlled). Optionally create a new
internal version at this point, then archive the replacement Web files.

Note: Various GDEX use cases are outlined above. Review them so that DOIs in
the GDEX are handled consistently.




:ref:`Back to Top <index>`
