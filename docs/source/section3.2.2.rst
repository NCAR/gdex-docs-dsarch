
.. _section3.2.2:

3.2.2 - Get Version Control
=====================


.. _GV:

Action Option -**GV** (-**GetVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves DOI/Version control records from GDEXDB for a
  given dataset.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](GV|GetVersion) [`Mode Option <mode_>`_]
|         [-(`FN|FieldNames <field_>`_) FieldNameString]
|         [-(`KV|KeyValue <section5.2_>`_) KeyNames]
|         [-(`OF|OutputFile <section5.1_>`_) OutputFileName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ option that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4_>`_)
     - formats each column to a uniform fixed width

  Use -`FN <section5.1_>`_ (-FieldNames) to specify which version control fields to retrieve.
  Defaults to 'VIEDSJX'. Use -`FN <section5.1_>`_ ALL to retrieve all available fields.

  Valid version control field names and their corresponding `Info <section5>`_ options:

=  =====  ======================================  =========================================================
   Names  `Info Options <section5>`_              Descriptions                                             
   V      -(`VI|VersionIndex <section5.2_>`_)     version control index                                    
   I      -(`IV|InternalVersion <section5.2_>`_)  Internal version number                                  
   E      -(`EV|ExternalVersion <section5.2_>`_)  External version number to publish                       
   D      -(`DN|DOINumber <section5.2_>`_)        DOI number created for the version control               
   S      -(`VT|VersionStatus <section5.2_>`_)    version control status, A-Active, P-Pending and H-History
   J      -(`BD|BeginDate <section5.2_>`_)        date the version control starts at                       
   K      -(`BT|BeginTime <section5.2_>`_)        time the version control starts at                       
   X      -(`ED|EndDate <section5.2_>`_)          date the terminated version control ends by              
   Y      -(`ET|EndTime <section5.2_>`_)          time the terminated version control ends by              
   N      -(`DE|Description <section5.2_>`_)      note for the version control record                      
=  =====  ======================================  =========================================================

  Use -`OF <section5.1_>`_ (-OutputFile) to save the retrieved information to a file. Without
  it, results are displayed on screen.


.. _3.2.2_e4:

**EXAMPLE 4. To retrieve all version control fields for d132000 and save to a file:**

  dsarch d132000 GV -`FN <section5.1_>`_ ALL -`OF <section5.1_>`_ d132000.vrsn

Content of output file d132000.vrsn:

Dataset<=>d132000
VersionIndex<:>InternalVersion<:>ExternalVersion<:>DOINumber<:>VersionStatus<:>BeginDate<:>BeginTime<:>EndDate<:>EndTime<:>Description<:>
9<:>1<:><:>10.5065/D6SQ8XDW<:>A<:>2013-03-04<:>14:38:44<:><:><:><:>




:ref:`Back to Top <index>`
