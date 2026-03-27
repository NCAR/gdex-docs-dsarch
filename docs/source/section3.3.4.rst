
.. _section3.3.4:

3.3.4 - Change Group Information
=====================


.. _CG:

Action Option -**CG** (-**ChangeGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

renumbers group indices for the specified dataset,
  mapping each original index (via -`OG <section5.2_>`_) to a new value (via -`GI <section5.2_>`_).

| **dsarch** [-(`DS|dataset <section5.1_>`_)] dNNNNNN [-](CG|ChangeGroup) [`Mode Options <mode_>`_]
|          -(`OG|OriginGroup <section5.2_>`_) OriginalGroupIndices
|          -(`GI|GroupIndex <section5.2_>`_) NewGroupIndices
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
     - resets the top group index for file records in the affected group
   * - -(`WN|WithFileNumber <section4_>`_)
     - re-evaluates and resets file counts for the affected groups

  Both -`OG <section5.2_>`_ (-OriginGroup) and -`GI <section5.2_>`_ (-GroupIndex) are required. All Saved and
  Web file records linked to the original indices are updated to the new
  values. The original indices must already exist in GDEXDB.


.. _3.3.4_e9:

**EXAMPLE 9. To reassign group indices 1 and 2 to 2 and 3 for d744004:**

  dsarch d744004 CG -`OG <section5.2_>`_ 1 2 -`GI <section5.2_>`_ 2 3




:ref:`Back to Top <index>`
