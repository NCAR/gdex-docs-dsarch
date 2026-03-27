
.. _section3.3.2:

3.3.2 - Get Group Information
=====================


.. _GG:

Action Option -**GG** (-**GetGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves group records for the specified dataset.
  Filter results by providing group indices, names, or a parent index.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN [-](GG|GetGroup)
|         [-(`FN|FieldNames <field_>`_) FieldNameString]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|         [-(`GN|GroupName <section5.2_>`_) GroupNames]
|         [-(`PI|ParentGroupIndex <section5.2_>`_) ParentGroupIndices]
|         [-(`OF|OutputFile <section5.1_>`_) OutputFileName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4_>`_)
     - formats each column to a uniform fixed width
   * - -(`RG|RecursiveGroup <section4_>`_)
     - gathers subgroups recursively for a given group index
   * - -(`WN|WithFileNumber <section4_>`_)
     - gathers and displays file counts for groups

  Use -`FN <section5.1_>`_ (-FieldNames) to specify which group fields to retrieve. Defaults
  to 'IGXTQSW'. Use -`FN <section5.1_>`_ ALL for all available fields.

  Valid group field names and their corresponding `Info <section5>`_ options:

=  =====  =====================================  ================================================
   Names  `Info Options <section5>`_             Descriptions                                    
   I      -(`GI|GroupIndex <section5.2_>`_)      group indices                                   
   G      -(`GN|GroupName <section5.2_>`_)       group names, IDs                                
   X      -(`PI|ParentIndex <section5.2_>`_)     parent group indices                            
   T      -(`TI|Title <section5.2_>`_)           group titles                                    
   R      -(`GT|GroupType <section5.2_>`_)       group types                                     
   P      -(`GP|GroupPattern <section5.2_>`_)    common file name patterns for each group        
   Q      -(`BF|BackupFlag <section5.2_>`_)      Quasar Backup flags                             
   A      -(`DA|DataAccessFlag <section5.2_>`_)  top group data file list access flags           
   S      -(`SP|SavedPath <section5.2_>`_)       path relative to saved home directory for groups
   W      -(`WP|WebPath <section5.2_>`_)         path relative to web home directory for groups  
   M      -(`ML|MetaLink <section5.2_>`_)        a link to content meta at the group level       
   D      -(`NW|NoteWeb <section5.2_>`_)         group description of data on GDEX Server        
   N      -(`NI|NoteInternal <section5.2_>`_)    group description of internal HPSS data         
=  =====  =====================================  ================================================

  Results can be filtered by group index (-`GI <section5.2_>`_), name (-`GN <section5.2_>`_), or parent index
  (-`PI <section5.2_>`_). The -`GN <section5.2_>`_ option accepts the '%' wildcard.


.. _3.3.2_e7:

**EXAMPLE 7. To retrieve the default group fields and file counts for groups**

  1 and 2 of d260001:

=  ============================================
   dsarch d260001 GG -`WN <section4_>`_ -GI 1 2
=  ============================================

Content of the output:

Dataset<=>d260001
GroupIndex<:>GroupName<:>ParentIndex<:>Title<:>GroupPattern<:>BackupFlag<:>SavedPath<:>WebPath<:>
1<:>DAILY<:>0<:>DAILY OAFlux Products<:><:>P<:><:>daily<:>
2<:>MONTHLY<:>0<:>MONTHLY OAFlux Products<:><:>P<:><:>monthly<:>




:ref:`Back to Top <index>`
