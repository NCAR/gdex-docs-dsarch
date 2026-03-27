
.. _section3.3.2:

3.3.2 - Get Group Information
=====================


.. _GG:

Action Option -**GG** (-**GetGroup**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves group records for the specified dataset.
  Filter results by providing group indices, names, or a parent index.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN [-](GG|GetGroup)
|           [-(:ref:`FN|FieldNames <FN>`) FieldNameString]
|           [-(:ref:`ON|OrderNames <ON>`) OrderNameString]
|           [-(:ref:`GI|GroupIndex <GI>`) GroupIndices]
|           [-(:ref:`GN|GroupName <GN>`) GroupNames]
|           [-(:ref:`PI|ParentGroupIndex <PI>`) ParentGroupIndices]
|           [-(:ref:`OF|OutputFile <OF>`) OutputFileName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.3.2:

  :ref:`Mode options <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - (:ref:`FO|FormatOutput <FO>`)
     - formats each column to a uniform fixed width
   * - (:ref:`RG|RecursiveGroup <RG>`)
     - gathers subgroups recursively for a given group index
   * - (:ref:`WN|WithFileNumber <WN>`)
     - gathers and displays file counts for groups

  Use -:ref:`FN <FN>` (-FieldNames) to specify which group fields to retrieve. Defaults
  to 'IGXTQSW'. Use -:ref:`FN <FN>` ALL for all available fields.

  Valid group field names and their corresponding :ref:`Info options <section5>`:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - I
     - (:ref:`GI|GroupIndex <GI>`)
     - group indices
   * - G
     - (:ref:`GN|GroupName <GN>`)
     - group names, IDs
   * - X
     - (:ref:`PI|ParentIndex <PI>`)
     - parent group indices
   * - T
     - (:ref:`TI|Title <TI>`)
     - group titles
   * - R
     - (:ref:`GT|GroupType <GT>`)
     - group types
   * - P
     - (:ref:`GP|GroupPattern <GP>`)
     - common file name patterns for each group
   * - Q
     - (:ref:`BF|BackupFlag <BF>`)
     - Quasar Backup flags
   * - A
     - (:ref:`DA|DataAccessFlag <DA>`)
     - top group data file list access flags
   * - S
     - (:ref:`SP|SavedPath <SP>`)
     - path relative to saved home directory for groups
   * - W
     - (:ref:`WP|WebPath <WP>`)
     - path relative to web home directory for groups
   * - M
     - (:ref:`ML|MetaLink <ML>`)
     - a link to content meta at the group level
   * - D
     - (:ref:`NW|NoteWeb <NW>`)
     - group description of data on GDEX Server
   * - N
     - (:ref:`NI|NoteInternal <NI>`)
     - group description of internal HPSS data

  Results can be filtered by group index (-:ref:`GI <GI>`), name (-:ref:`GN <GN>`), or parent index
  (-:ref:`PI <PI>`). The -:ref:`GN <GN>` option accepts the '%' wildcard.


.. _3.3.2_e7:

**EXAMPLE 7. To retrieve the default group fields and file counts for groups 1 and 2 of d260001:**

| **dsarch** d260001 :ref:`GG <GG>` -:ref:`WN <WN>` -:ref:`GI <GI>` 1 2

Content of the output:

.. code-block:: none

   Dataset<=>d260001
   GroupIndex<:>GroupName<:>ParentIndex<:>Title<:>GroupPattern<:>BackupFlag<:>SavedPath<:>WebPath<:>
   1<:>DAILY<:>0<:>DAILY OAFlux Products<:><:>P<:><:>daily<:>
   2<:>MONTHLY<:>0<:>MONTHLY OAFlux Products<:><:>P<:><:>monthly<:>
   2 group records retrieved
   d260001-G1: DS-11094192261 DC-327 WC-327 SS-8909173908 SC-51
   d260001-G2: DS-552780725 DC-522 WC-522 SS-465789806 SC-51




:ref:`Back to Top <index>`
