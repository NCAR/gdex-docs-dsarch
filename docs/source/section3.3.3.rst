
.. _section3.3.3:

3.3.3 - Delete Group Information
=====================


.. _DG:

Action Option -**DG** (-**DeleteGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

deletes one or multiple groups from RDADB for given
  group indices of a specified dataset.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](DG|DeleteGroup) [`Mode Options <#mode>`_]
|   -(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices
|   [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for deleting group action:

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

  The groups to be deleted are identified by group indices given per `Info <section5.rst>`_
  option -`GI <section5.2.rst#GI>`_ (-GroupIndex) and dataset number per option -`DS <section5.1.rst#DS>`_. This action
  is blocked if there exist any subgroups or data files under the groups to
  be deleted.  To delete the groups with files under them, you gather the files
  on Saved or RDA Server per action options, -`GS <section3.4.2.rst>`_ (-GetSavedFile) or -`GW <section3.4.4.rst>`_
  (-GetWebFile), and set the group indices of the files to 0 or change them to
  other group indices via action -`CG <section3.3.4.rst>`_ (-ChangeGroup), or delete the files
  gathered per action -`DL <section3.4.15.rst>`_ (-Delete); then delete the groups.


.. _e8:

**EXAMPLE 8. **

 Delete Group Indices 2 And 3 Of D744004

  dsarch d744004 DG -`GI <section5.2.rst#GI>`_ 2 3



.. raw:: html

   <br>

:ref:`Back to Top <index>`
