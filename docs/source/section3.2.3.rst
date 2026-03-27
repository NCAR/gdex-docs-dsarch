
.. _section3.2.3:

3.2.3 - Terminate Version Control
=====================


.. _TV:

Action Option -**TV** (-**TerminateVersion**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

closes a version control record in GDEXDB for the
  specified dataset, marking it as history or removing it if still pending.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN [-](TV|TerminateVersion) [:ref:`Mode Options <mode3.2.3>`]
|            -(:ref:`VI|VersionIndex <VI>`) VersionIndex
|           [-(:ref:`LN|LoginName <LN>`) LoginAccountName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.2.3:

  :ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - \-(:ref:`MD|MyDataset <MD>`)
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - \-(:ref:`NT|NoTrim <NT>`)
     - skips trimming of spaces and comments from input values, speeding up input file processing

  Provide the version index via -:ref:`VI <VI>` and the dataset number via -:ref:`DS <DS>`. Termination
  is blocked if any Web files are still linked to that version. To work around
  this, first list those files using -:ref:`GW <GW>` (-GetWebFile), then either reassign
  their version index (to 0 or another value) or convert them to Saved files;
  only then can the version be terminated.


.. _3.2.3_e5:

**EXAMPLE 5. To terminate version index 5 of d999009:**

| **dsarch** d999009 :ref:`TV <TV>` -:ref:`VI <VI>` 5

  Active records are moved to 'H' (History) status and kept for future
  reference. Pending records are deleted from GDEXDB entirely.




:ref:`Back to Top <index>`
