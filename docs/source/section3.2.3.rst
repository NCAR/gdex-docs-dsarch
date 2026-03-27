
.. _section3.2.3:

3.2.3 - Terminate Version Control
=====================


.. _TV:

Action Option -**TV** (-**TerminateVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

closes a version control record in GDEXDB for the
  specified dataset, marking it as history or removing it if still pending.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](TV|TerminateVersion) [`Mode Options <mode_>`_]
|          -(`VI|VersionIndex <section5.2_>`_) VersionIndex
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

  Provide the version index via -`VI <section5.2_>`_ and the dataset number via -`DS <section5.1_>`_. Termination
  is blocked if any Web files are still linked to that version. To work around
  this, first list those files using -`GW <section3.4.4_>`_ (-GetWebFile), then either reassign
  their version index (to 0 or another value) or convert them to Saved files;
  only then can the version be terminated.


.. _3.2.3_e5:

**EXAMPLE 5. To terminate version index 5 of d999009:**

  dsarch d999009 TV -`VI <section5.2_>`_ 5

  Active records are moved to 'H' (History) status and kept for future
  reference. Pending records are deleted from GDEXDB entirely.




:ref:`Back to Top <index>`
