
.. _section3.3.3:

3.3.3 - Delete Group Information
=====================


.. _DG:

Action Option -**DG** (-**DeleteGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

removes one or more group records from GDEXDB for the
specified dataset.

.. code-block:: bash

  **dsarch** [:ref:`-(DS|Dataset) <DS>`] dNNNNNN [-](DG|DeleteGroup) [:ref:`Mode Options <mode3.3.3>`]
          :ref:`-(GI|GroupIndex) <GI>` GroupIndices
         [:ref:`-(LN|LoginName) <LN>` LoginAccountName]
         [:ref:`-(DB|Debug) <DB>` DebugModeInfo]

.. _mode3.3.3:

:ref:`Mode options <section4>` that can be specified for this action:

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

Specify groups by index via -:ref:`GI <GI>` and the dataset via -:ref:`DS <DS>`. Deletion is blocked
if a group still contains subgroups or data files. To delete a non-empty
group, first retrieve its files with -:ref:`GS <GS>` (-GetSavedFile) or -:ref:`GW <GW>`
(-GetWebFile), then either move them to another group via -:ref:`CG <CG>` (-ChangeGroup),
reset their group index to 0, or remove them with -:ref:`DL <DL>` (-Delete). Once empty,
the group can be deleted.


.. _3.3.3_e8:

**EXAMPLE 8. To delete group indices 2 and 3 of d744004:**

.. code-block:: bash

  **dsarch** d744004 :ref:`DG <DG>` -:ref:`GI <GI>` 2 3




:ref:`Back to Top <index>`
