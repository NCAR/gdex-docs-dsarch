
.. _section3.3.4:

3.3.4 - Change Group Information
=================================


.. _CG:

Action Option -**CG** (-**ChangeGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

renumbers group indices for the specified
dataset, mapping each original index (via :ref:`-OG <OG>`) to a new value (via
:ref:`-GI <GI>`).

| **dsarch** [:ref:`-(DS|dataset) <DS>`] dNNNNNN [-](CG|ChangeGroup) [:ref:`Mode Options <mode3.3.4>`]
|            :ref:`-(OG|OriginGroup) <OG>` OriginalGroupIndices
|            :ref:`-(GI|GroupIndex) <GI>` NewGroupIndices
|           [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
|           [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

Available mode options:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(MD|MyDataset) <MD>`
     - allows any specialist to set GDEXDB information, regardless of dataset ownership
   * - :ref:`-(NT|NoTrim) <NT>`
     - skips trimming of spaces and comments from input values, speeding up input file processing
   * - :ref:`-(RT|ResetTGroup) <RT>`
     - resets the top group index for file records in the affected group
   * - :ref:`-(WN|WithFileNumber) <WN>`
     - re-evaluates and resets file counts for the affected groups

Both :ref:`-OG <OG>` (-OriginGroup) and :ref:`-GI <GI>` (-GroupIndex) are required. All Saved
and Web file records linked to the original indices are updated to
the new values. The original indices must already exist in GDEXDB.


.. _3.3.4_e9:

**EXAMPLE 9. To reassign group indices 1 and 2 to 2 and 3 for d744004:**

| **dsarch** d744004 :ref:`CG <CG>` :ref:`-OG <OG>` 1 2 :ref:`-GI <GI>` 2 3



| :ref:`Back to Top <section3.3.4>`
| :ref:`Back to Table of Contents <index>`
