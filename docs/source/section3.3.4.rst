
.. _section3.3.4:

3.3.4 - Change Group Information
=====================


.. _CG:

Action Option -**CG** (-**ChangeGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

changes group indices from original groups given by
  option -`OG <section5.2.rst#OG>`_ (-OriginGroup) to new groups specified by option -`GI <section5.2.rst#GI>`_ (-GroupIndex)
  for a given dataset.

| **dsarch** [-(`DS|dataset <section5.1.rst#DS>`_)] dsnnn.n [-](CG|ChangeGroup) [`Mode Options <#mode>`_]
|   -(`OG|OriginGroup <section5.2.rst#OG>`_) OriginalGroupIndices
|   -(`GI|GroupIndex <section5.2.rst#GI>`_) NewGroupIndices
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for changing group action:

.. list-table::
   :widths: auto

   * - -(`MD|MyDataset <section4.rst#MD>`_)
     - overrides the default specialist and enables RDADB information to be set by any one
   * - -(`NT|NoTrim <section4.rst#NT>`_)
     - skip trimming of spaces and comments from input values to speed up reading input file(s)
   * - -(`RT|ResetTGroup <section4.rst#RT>`_)
     - reset top group index for the HPSS/Web file records
   * - -(`WN|WithFileNumber <section4.rst#WN>`_)
     - reevaluates and resets HPSS/Web file counts for the affected groups

  A dataset group is identified by its group index. It can only be changed to
  different value via this action -`CG <#CG>`_ and both original group indices per `Info <section5.rst>`_
  option -`OG <section5.2.rst#OG>`_ (-OriginGroup) and new group indices per `Info <section5.rst>`_ option -`GI <section5.2.rst#GI>`_
  (-GroupIndex) are present. The Saved and Web File namesassociated to the
  original group indices are changed to new group indices correspondingly. The
  original group indices must exist in RDADB for the given dataset.


.. _e9:

**EXAMPLE 9. **

 Change Group Indices 1 And 2, To 2 And 3 Of D744004

  dsarch d744004 CG -`OG <section5.2.rst#OG>`_ 1 2 -`GI <section5.2.rst#GI>`_ 2 3



.. raw:: html

   <br>

:ref:`Back to Top <index>`
