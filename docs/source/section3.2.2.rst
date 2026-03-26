
.. _section3.2.2:

3.2.2 - Get Version Control
=====================


.. _GV:

Action Option -**GV** (-**GetVersion**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves DOI/Version control information from RDADB for a given
  dataset number.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](GV|GetVersion) [`Mode Option <#mode>`_]
|   [-(`FN|FieldNames <#field>`_) FieldNameString]
|   [-(`KV|KeyValue <section5.2.rst#KV>`_) KeyNames]
|   [-(`OF|OutputFile <section5.1.rst#OF>`_) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ option that can be specified for getting DOI/Version control Action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4.rst#FO>`_)
     - format the column output with a same width for all values of a given field

.. _field:

  Use `Info <section5.rst>`_ option -`FN <section5.1.rst#FN>`_ (-FieldNames) to specify what version control fields to retrieve.
  It defaults to 'VIEDSJX' if option -`FN <section5.1.rst#FN>`_ is omitted. Information of all available
  fields is retrieved if -`FN <section5.1.rst#FN>`_ ALL is given.

  Valid version control field names and their corresponding `Info <section5.rst>`_ options:

=  =====  ============================================  =========================================================
   Names  `Info Options <section5.rst>`_                Descriptions                                             
   V      -(`VI|VersionIndex <section5.2.rst#VI>`_)     version control index                                    
   I      -(`IV|InternalVersion <section5.2.rst#IV>`_)  Internal version number                                  
   E      -(`EV|ExternalVersion <section5.2.rst#EV>`_)  External version number to publish                       
   D      -(`DN|DOINumber <section5.2.rst#DN>`_)        DOI number created for the version control               
   S      -(`VT|VersionStatus <section5.2.rst#VT>`_)    version control status, A-Active, P-Pending and H-History
   J      -(`BD|BeginDate <section5.2.rst#BD>`_)        date the version control starts at                       
   K      -(`BT|BeginTime <section5.2.rst#BT>`_)        time the version control starts at                       
   X      -(`ED|EndDate <section5.2.rst#ED>`_)          date the terminated version control ends by              
   Y      -(`ET|EndTime <section5.2.rst#ET>`_)          time the terminated version control ends by              
   N      -(`DE|Description <section5.2.rst#DE>`_)      note for the version control record                      
=  =====  ============================================  =========================================================

  `Info <section5.rst>`_ option -`OF <section5.1.rst#OF>`_ (-OutputFile) is used to specify a file name to save the
  retrieved information for later usage. Result of this action is displayed
  on screen if no output file is provided.


.. _e4:

**EXAMPLE 4. **

Get Version Control Information Of D132000 For All Fields And Dump The
  output into file 'd132000.vrsn'

  dsarch d132000 GV -`FN <section5.1.rst#FN>`_ ALL -`OF <section5.1.rst#OF>`_ d132000.vrsn

Content of output file d132000.vrn:

Dataset<=>d132000
VersionIndex<:>InternalVersion<:>ExternalVersion<:>DOINumber<:>VersionStatus<:>BeginDate<:>BeginTime<:>EndDate<:>EndTime<:>Description<:>
9<:>1<:><:>10.5065/D6SQ8XDW<:>A<:>2013-03-04<:>14:38:44<:><:><:><:>



.. raw:: html

   <br>

:ref:`Back to Top <index>`
