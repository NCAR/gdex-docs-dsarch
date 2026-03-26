
.. _section3.1.2:

3.1.2 - Get Dataset Information
=====================


.. _GD:

Action Option -**GD** (-**GetDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves dataset information from RDADB for a given
  dataset number.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n [-](GD|GetDataset) [`Mode Options <#mode>`_]
|   [-(`FN|FieldNames <#field>`_) FieldNameString]
|   [-(`KV|KeyValue <section5.2.rst#KV>`_) KeyNames]
|   [-(`OF|OutputFile <section5.1.rst#OF>`_) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for getting dataset Action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4.rst#FO>`_)
     - format the column output with a same width for all values of a given field
   * - -(`PE|ShowPeriod <section4.rst#PE>`_)
     - show associated period information for dataset, and groups if any
   * - -(`WN|WithFileNumber <section4.rst#WN>`_)
     - gathers and displays Saved/Web file counts

.. _field:

  Use `Info <section5.rst>`_ option -`FN <section5.1.rst#FN>`_ (-FieldNames) to specify what dataset fields to retrieve.
  It defaults to 'SWFULQ' if option -`FN <section5.1.rst#FN>`_ is omitted. Information of all available
  fields is retrieved if -`FN <section5.1.rst#FN>`_ ALL is given.

  Valid dataset field names and their corresponding `Info <section5.rst>`_ options:

=  =====  ===========================================  =============================================
   Names  `Info Options <section5.rst>`_               Descriptions                                 
   T      -(`TI|Title <section5.2.rst#TI>`_)           dataset title                                
   S      -(`SP|SavedPath <section5.2.rst#SP>`_)       path relative to Saved home directory        
   H      -(`WH|WebHome <section5.2.rst#WH>`_)         path for the web data home directory         
   W      -(`WP|WebPath <section5.2.rst#WP>`_)         path relative to web home directory          
   F      -(`DF|DataFormat <section5.2.rst#DF>`_)      default data content format                  
   U      -(`UD|UseDSARCH <section5.1.rst#UD>`_)       use DSARCH flag                              
   L      -(`LC|Location <section5.2.rst#LC>`_)        Online web file access location flags        
   Q      -(`BF|BackupFlag <section5.2.rst#BF>`_)      Quasar Backup flags                          
   A      -(`DA|DataAccessFlag <section5.2.rst#DA>`_)  dataset data file list access flags          
   V      -(`GL|GroupLevel <section5.2.rst#GL>`_)      number of group levels to display            
   C      -(`FL|FileLimit <section5.1.rst#FL>`_)       file count limit for separate group filelists
   B      -(`BL|ButtonLimit <section5.1.rst#BL>`_)     file count limit for showing script buttons  
   M      -(`ML|MetaLink <section5.2.rst#ML>`_)        a link to content meta at the dataset level  
   W      -(`NW|NoteWeb <section5.2.rst#NW>`_)         web data description                         
   I      -(`NI|NoteInternal <section5.2.rst#NI>`_)    internal data description                    
   D      -(`ND|NoteDocument <section5.2.rst#ND>`_)    document description                         
   N      -(`NS|NoteSoftware <section5.2.rst#NS>`_)    software description                         
   G      -(`GI|GroupIndex <section5.2.rst#GI>`_)      Group Indices to identify groups for periods 
   J      -(`BD|BeginDate <section5.2.rst#BD>`_)       date data begin for dataset/group            
   K      -(`BT|BeginTime <section5.2.rst#BT>`_)       time data begin for dataset/group            
   X      -(`ED|EndDate <section5.2.rst#ED>`_)         date data end for dataset/group              
   Y      -(`ET|EndTime <section5.2.rst#ET>`_)         time data end for dataset/group              
=  =====  ===========================================  =============================================

  `Info <section5.rst>`_ option -`OF <section5.1.rst#OF>`_ (-OutputFile) is used to specify a file name to save the
  retrieved information for later usage. Result of this action is displayed
  on screen if no output file is provided.


.. _e2:

**EXAMPLE 2. **

Get Dataset Information Of D260001 For All Fields And Dump The
  output into file 'd260001.ds'

  dsarch d260001 GD -`FN <section5.1.rst#FN>`_ ALL -`PE <section4.rst#PE>`_ -OF d260001.ds

Content of output file d260001.ds:

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



.. raw:: html

   <br>

:ref:`Back to Top <index>`
