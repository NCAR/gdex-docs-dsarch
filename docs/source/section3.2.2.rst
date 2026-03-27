
.. _section3.2.2:

3.2.2 - Get Version Control
=====================


.. _GV:

Action Option -**GV** (-**GetVersion**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

retrieves DOI/Version control records from GDEXDB for a
  given dataset.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN [-](GV|GetVersion) [:ref:`Mode Option <mode3.2.2>`]
|           [-(:ref:`FN|FieldNames <FN>`) FieldNameString]
|           [-(:ref:`KV|KeyValue <KV>`) KeyNames]
|           [-(:ref:`OF|OutputFile <OF>`) OutputFileName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.2.2:

  :ref:`Mode option <section4>` that can be specified for this action:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - ``-``(:ref:`FO|FormatOutput <FO>`)
     - formats each column to a uniform fixed width

  Use -:ref:`FN <FN>` (-FieldNames) to specify which version control fields to retrieve.
  Defaults to 'VIEDSJX'. Use -:ref:`FN <FN>` ALL to retrieve all available fields.

  Valid version control field names and their corresponding :ref:`Info options <section5>`:

.. list-table::
   :widths: auto
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - V
     - ``-``(:ref:`VI|VersionIndex <VI>`)
     - version control index
   * - I
     - ``-``(:ref:`IV|InternalVersion <IV>`)
     - Internal version number
   * - E
     - ``-``(:ref:`EV|ExternalVersion <EV>`)
     - External version number to publish
   * - D
     - ``-``(:ref:`DN|DOINumber <DN>`)
     - DOI number created for the version control
   * - S
     - ``-``(:ref:`VT|VersionStatus <VT>`)
     - version control status, A-Active, P-Pending and H-History
   * - J
     - ``-``(:ref:`BD|BeginDate <BD>`)
     - date the version control starts at
   * - K
     - ``-``(:ref:`BT|BeginTime <BT>`)
     - time the version control starts at
   * - X
     - ``-``(:ref:`ED|EndDate <ED>`)
     - date the terminated version control ends by
   * - Y
     - ``-``(:ref:`ET|EndTime <ET>`)
     - time the terminated version control ends by
   * - N
     - ``-``(:ref:`DE|Description <DE>`)
     - note for the version control record

  Use -:ref:`OF <OF>` (-OutputFile) to save the retrieved information to a file. Without
  it, results are displayed on screen.


.. _3.2.2_e4:

**EXAMPLE 4. To retrieve all version control fields for d132000 and save to a file:**

| **dsarch** d132000 :ref:`GV <GV>` -:ref:`FN <FN>` ALL -:ref:`OF <OF>` d132000.vrsn

Content of output file d132000.vrsn:

.. code-block:: none

   Dataset<=>d132000
   VersionIndex<:>InternalVersion<:>ExternalVersion<:>DOINumber<:>VersionStatus<:>BeginDate<:>BeginTime<:>EndDate<:>EndTime<:>Description<:>
   9<:>1<:><:>10.5065/D6SQ8XDW<:>A<:>2013-03-04<:>14:38:44<:><:><:><:>




:ref:`Back to Top <index>`
