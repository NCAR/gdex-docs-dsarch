
.. _section3.3.3:

3.3.3 - Delete Group Information
=====================


.. _DG:

Action Option -**DG** (-**DeleteGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

removes one or more group records from GDEXDB for the
  specified dataset.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](DG|DeleteGroup) [`Mode Options <mode_>`_]
|          -(`GI|GroupIndex <section5.2_>`_) GroupIndices
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

  Specify groups by index via -`GI <section5.2_>`_ and the dataset via -`DS <section5.1_>`_. Deletion is blocked
  if a group still contains subgroups or data files. To delete a non-empty
  group, first retrieve its files with -`GS <section3.4.2_>`_ (-GetSavedFile) or -`GW <section3.4.4_>`_
  (-GetWebFile), then either move them to another group via -`CG <section3.3.4_>`_ (-ChangeGroup),
  reset their group index to 0, or remove them with -`DL <section3.4.15_>`_ (-Delete). Once empty,
  the group can be deleted.


.. _3.3.3_e8:

**EXAMPLE 8. To delete group indices 2 and 3 of d744004:**

  dsarch d744004 DG -`GI <section5.2_>`_ 2 3




:ref:`Back to Top <index>`
