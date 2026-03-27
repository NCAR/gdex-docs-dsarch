
.. _section3.1.2:

3.1.2 - Get Dataset Information
=====================


.. _GD:

Action Option -**GD** (-**GetDataset**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

reads and displays dataset record fields from GDEXDB
  for the specified dataset.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](GD|GetDataset) [`Mode Options <mode_>`_]
|         [-(`FN|FieldNames <field_>`_) FieldNameString]
|         [-(`KV|KeyValue <section5.2_>`_) KeyNames]
|         [-(`OF|OutputFile <section5.1_>`_) OutputFileName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4_>`_)
     - formats each column to a uniform fixed width
   * - -(`PE|ShowPeriod <section4_>`_)
     - includes associated period information for the dataset and any groups
   * - -(`WN|WithFileNumber <section4_>`_)
     - gathers and displays Saved/Web file counts

  Use -`FN <section5.1_>`_ (-FieldNames) to select which dataset fields to include. Defaults
  to 'SWFULQ'. Use -`FN <section5.1_>`_ ALL to retrieve every available field.

  Valid dataset field names and their corresponding `Info <section5>`_ options:

=  =====  =====================================  =============================================
   Names  `Info Options <section5>`_             Descriptions                                 
   T      -(`TI|Title <section5.2_>`_)           dataset title                                
   S      -(`SP|SavedPath <section5.2_>`_)       path relative to Saved home directory        
   H      -(`WH|WebHome <section5.2_>`_)         path for the web data home directory         
   W      -(`WP|WebPath <section5.2_>`_)         path relative to web home directory          
   F      -(`DF|DataFormat <section5.2_>`_)      default data content format                  
   U      -(`UD|UseDSARCH <section5.1_>`_)       use DSARCH flag                              
   L      -(`LC|Location <section5.2_>`_)        Online web file access location flags        
   Q      -(`BF|BackupFlag <section5.2_>`_)      Quasar Backup flags                          
   A      -(`DA|DataAccessFlag <section5.2_>`_)  dataset data file list access flags          
   V      -(`GL|GroupLevel <section5.2_>`_)      number of group levels to display            
   C      -(`FL|FileLimit <section5.1_>`_)       file count limit for separate group filelists
   B      -(`BL|ButtonLimit <section5.1_>`_)     file count limit for showing script buttons  
   M      -(`ML|MetaLink <section5.2_>`_)        a link to content meta at the dataset level  
   W      -(`NW|NoteWeb <section5.2_>`_)         web data description                         
   I      -(`NI|NoteInternal <section5.2_>`_)    internal data description                    
   D      -(`ND|NoteDocument <section5.2_>`_)    document description                         
   N      -(`NS|NoteSoftware <section5.2_>`_)    software description                         
   G      -(`GI|GroupIndex <section5.2_>`_)      Group Indices to identify groups for periods 
   J      -(`BD|BeginDate <section5.2_>`_)       date data begin for dataset/group            
   K      -(`BT|BeginTime <section5.2_>`_)       time data begin for dataset/group            
   X      -(`ED|EndDate <section5.2_>`_)         date data end for dataset/group              
   Y      -(`ET|EndTime <section5.2_>`_)         time data end for dataset/group              
=  =====  =====================================  =============================================

  Use -`OF <section5.1_>`_ (-OutputFile) to save the retrieved information to a file. Without
  it, results are displayed on screen.


.. _3.1.2_e2:

**EXAMPLE 2. To retrieve all dataset fields for d260001 and save to a file:**

  dsarch d260001 GD -`FN <section5.1_>`_ ALL -`PE <section4_>`_ -OF d260001.ds

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




:ref:`Back to Top <index>`
