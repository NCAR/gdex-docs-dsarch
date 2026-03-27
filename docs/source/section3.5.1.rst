
.. _section3.5.1:

3.5.1 - Get All Information
=====================


.. _GA:

Action Option -**GA** (-**GetALL**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

exports all dataset, group, and Saved/Web/Help/Quasar file
records for a dataset in one step. Equivalent to running -:ref:`GD <GD>`, -:ref:`GG <GG>`, -:ref:`GS <GS>`, -:ref:`GW <GW>`,
-:ref:`GH <GH>`, and -:ref:`GQ <GQ>` together.

|  **dsarch** [:ref:`-(DS|dataset) <DS>`] dNNNNNN -(GA|GetAll)
|             [:ref:`-(OF|OutputFile) <OF>` OutputFileName]
|             [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

No :ref:`Mode options <section4>` apply to this action; all available fields are retrieved
for every record type.

Output is organized under [DATASET], [DSGROUP], [SAVEDFILE], [WEBFILE],
[HELPFILE], and [QUASARFILE] sections.

Use -:ref:`OF <OF>` (-OutputFile) to write results to a file; without it, results print
to screen. The output file can be edited and fed back to -:ref:`SA <SA>` (-SetAll) to
apply changes in bulk.




:ref:`Back to Top <index>`
