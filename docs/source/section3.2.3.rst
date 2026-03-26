
.. _section3.2.3:

3.2.3 - Terminate Version Control
=====================


.. _TV:

Action Option -**TV** (-**TerminateVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

terminates a version control from RDADB for a specified dataset.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](TV|TerminateVersion) [`Mode Options <#mode>`_]
|   -(`VI|VersionIndex <section5.2.rst#VI>`_) VersionIndix
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for terminating version control action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)

  The version control record to be terminated is identified by the version index given
  per `Info <section5.rst>`_ option -`VI <section5.2.rst#VI>`_ (-VersionIndex) and dataset number per option -`DS <section5.1.rst#DS>`_. This action
  is blocked if there exist any Web data files lined to the version index. To terminate
  the version control record with Web files under it, you gather the Web file names per
  action option -`GW <section3.4.4.rst>`_ (-GetWebFile), and either set the version index value to 0 or a
  different index, or move the Web files to Saved files; then terminate the version
  control.


.. _e5:

**EXAMPLE 5. **

 Terminate Version Index 5 Of D999009

  dsarch d999009 TV -`VI <section5.2.rst#VI>`_ 5

  After termination, an active version control record is changed to status 'H' and the
  record is retained for future references, but for a Pending version control record, it
  is completely removed from RDADB if it is terminated.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
