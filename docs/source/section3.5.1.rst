
.. _section3.5.1:

3.5.1 - Get All Information
=====================


.. _GA:

Action Option -**GA** (-**GetALL**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

exports all dataset, group, and Saved/Web/Help/Quasar file
  records for a dataset in one step. Equivalent to running -`GD <section3.1.2_>`_, -`GG <section3.3.2_>`_, -`GS <section3.4.2_>`_, -`GW <section3.4.4_>`_,
  -`GH <section3.4.6_>`_, and -`GQ <section3.4.8_>`_ together.

| **dsarch** [-(`DS|dataset <section5.1_>`_)] dNNNNNN -(GA|GetAll)
|         [-(`OF|OutputFile <section5.1_>`_) OutputFileName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

  No `Mode <section4>`_ options apply to this action; all available fields are retrieved
  for every record type.

  Output is organized under [DATASET], [DSGROUP], [SAVEDFILE], [WEBFILE],
  [HELPFILE], and [QUASARFILE] sections.

  Use -`OF <section5.1_>`_ (-OutputFile) to write results to a file; without it, results print
  to screen. The output file can be edited and fed back to -`SA <section3.5.2_>`_ (-SetAll) to
  apply changes in bulk.




:ref:`Back to Top <index>`
