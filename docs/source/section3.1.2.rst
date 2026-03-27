
.. _section3.1.2:

3.1.2 - Get Dataset Information
=====================


.. _GD:

Action Option -**GD** (-**GetDataset**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

reads and displays dataset record fields from GDEXDB
  for the specified dataset.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN [-](GD|GetDataset) [:ref:`Mode Options <mode3.1.2>`]
|           [-(:ref:`FN|FieldNames <FN>`) FieldNameString]
|           [-(:ref:`KV|KeyValue <KV>`) KeyNames]
|           [-(:ref:`OF|OutputFile <OF>`) OutputFileName]
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

.. _mode3.1.2:

:ref:`Mode options <section4>` that can be specified for this action

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`-(FO|FormatOutput) <FO>`
     - formats each column to a uniform fixed width
   * - :ref:`-(PE|ShowPeriod) <PE>`
     - includes associated period information for the dataset and any groups
   * - :ref:`-(WN|WithFileNumber) <WN>`
     - gathers and displays Saved/Web file counts


Use -:ref:`FN <FN>` (-FieldNames) to select which dataset fields to include. Defaults
to 'SWFULQ'. Use -:ref:`FN <FN>` ALL to retrieve every available field.



.. list-table:: Optional Table Title
   :widths: 20 20 60
   :header-rows: 1

   * - Header Col 1
     - Header Col 2
     - Header Col 3
   * - T
     - :ref:`-(TI|Title) <TI>`
     - dataset title
   * - Row 1, Cell 1
     - Row 1, Cell 2
     - Row 1, Cell 3
   * - Row 2, Cell 1
     - Row 2, Cell 2
     - Row 2, Cell 3


.. list-table:: Valid dataset field names and their corresponding :ref:`Info options <section5>`
   :widths: 10 30 50
   :header-rows: 1

   * - Names
     - :ref:`Info Options <section5>`
     - Descriptions
   * - T
     - :ref:`-(TI|Title) <TI>`
     - dataset title
   * - S
     - :ref:`-(SP|SavedPath) <SP>`
     - path relative to Saved home directory
   * - H
     - :ref:`-(WH|WebHome) <WH>`
     - path for the web data home directory
   * - W
     - :ref:`-(WP|WebPath) <WP>`
     - path relative to web home directory
   * - F
     - :ref:`-(DF|DataFormat) <DF>`
     - default data content format
   * - U
     - :ref:`-(UD|UseDSARCH) <UD>`
     - use DSARCH flag
   * - X
     - :ref:`-(ED|EndDate) <ED>`
     - date data end for dataset/group
   * - Y
     - :ref:`-(ET|EndTime) <ET>`
     - time data end for dataset/group


  Use -:ref:`OF <OF>` (-OutputFile) to save the retrieved information to a file. Without
  it, results are displayed on screen.


.. _3.1.2_e2:

**EXAMPLE 2. To retrieve all dataset fields for d260001 and save to a file:**

| **dsarch** d260001 :ref:`GD <GD>` -:ref:`FN <FN>` ALL -:ref:`PE <PE>` -:ref:`OF <OF>` d260001.ds

Content of output file d260001.ds:

.. code-block:: none

   Dataset<=>d260001
   Title<=>Objectively Analyzed Air-Sea Fluxes (OAFlux) For Global Oceans, By Lisan Yu et al.
   SavedPath<=>
   WebPath<=>
   Location<=>G
   DataFormat<=>
   UseDSARCH<=>P
   GroupLevel<=>3
   FileLimit<=>500
   ButtonLimit<=>2
   DescWeb<=>
   DescInternal<=>
   GroupIndex<:>BeginDate<:>EndDate<:>BeginTime<:>EndTime<:>
   1<:>1985-01-01<:>2006-12-31<:>00:00:00<:>00:00:59<:>
   2<:>1958-01-01<:>2006-12-31<:>00:00:00<:>00:00:59<:>




:ref:`Back to Top <index>`
