
.. _section3.3.2:

3.3.2 - Get Group Information
=====================


.. _GG:

Action Option -**GG** (-**GetGroup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves group information for a given dataset. Information
  of specified groups are retrieved if the group indices or names are provided.

| **dsarch** [-(`DS <section5.1.rst#DS>`_|Dataset] dsnnn.n [-](GG|GetGroup)
|   [-(`FN|FieldNames <#field>`_) FieldNameString]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`GN|GroupName <section5.2.rst#GN>`_) GroupNames]
|   [-(`PI|ParentGroupIndex <section5.2.rst#PI>`_) ParentGroupIndices]
|   [(-`OF <section5.1.rst#OF>`_|-OutputFile) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for getting group action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4.rst#FO>`_)
     - format the column output with a same width for all values of a given field
   * - -(`RG|REcursiveGroup <section4.rst#RG>`_)
     - gather subgroups recursively for given group index
   * - -(`WN|WithFileNumber <section4.rst#WN>`_)
     - gathers and displays HPSS/Web file counts for groups

.. _field:

  Use `Info <section5.rst>`_ option -`FN <section5.1.rst#FN>`_ (-FieldNames) to specify what group fields to retrieve.
  It defaults to 'IGXTQSW' if option -`FN <section5.1.rst#FN>`_ is not provided. Information of all
  available fields is retrieved if -`FN <section5.1.rst#FN>`_ ALL is given.

  Valid group field names and their corresponding `Info <section5.rst>`_ options:

=  =====  ===========================================  ================================================
   Names  `Info Options <section5.rst>`_               Descriptions                                    
   I      -(`GI|GroupIndex <section5.2.rst#GI>`_)      group indices                                   
   G      -(`GN|GroupName <section5.2.rst#GN>`_)       group names, IDs                                
   X      -(`PI|ParentIndex <section5.2.rst#PI>`_)     parent group indices                            
   T      -(`TI|Title <section5.2.rst#TI>`_)           group titles                                    
   R      -(`GT|GroupType <section5.2.rst#GT>`_)       group types                                     
   P      -(`GP|GroupPattern <section5.2.rst#GP>`_)    common file name patterns for each group        
   Q      -(`BF|BackupFlag <section5.2.rst#BF>`_)      Quasar Backup flags                             
   A      -(`DA|DataAccessFlag <section5.2.rst#DA>`_)  top group data file list access flags           
   S      -(`SP|SavedPath <section5.2.rst#SP>`_)       path relative to saved home directory for groups
   W      -(`WP|WebPath <section5.2.rst#WP>`_)         path relative to web home directory for groups  
   M      -(`ML|MetaLink <section5.2.rst#ML>`_)        a link to content meta at the group level       
   D      -(`NW|NoteWeb <section5.2.rst#NW>`_)         group description of data on RDA Server         
   N      -(`NI|NoteInternal <section5.2.rst#NI>`_)    group description of internal HPSS data         
=  =====  ===========================================  ================================================

  Group information can be retrieved for specified groups per option -`GI <section5.2.rst#GI>`_
  (-GroupIndex) or -`GN <section5.2.rst#GN>`_ (-GroupName), or per option -`PI <section5.2.rst#PI>`_ (-ParentIndex). `Info <section5.rst>`_
  option -`GN <section5.2.rst#GN>`_ accepts wildcard input of '%' for matching any number of
  characters.


.. _e7:

**EXAMPLE 7. **

Get The Group Information Of D260001 For Default Fields And
  the file counts for groups 1 and 2

  dsarch d260001 GG -`WN <section4.rst#WN>`_ -GI 1 2

Content of the output:

Dataset<=>d260001
GroupIndex<:>GroupName<:>ParentIndex<:>Title<:>GroupPattern<:>BackupFlag<:>SavedPath<:>WebPath<:>
1<:>DAILY<:>0<:>DAILY OAFlux Products<:><:>P<:><:>daily<:>
2<:>MONTHLY<:>0<:>MONTHLY OAFlux Products<:><:>P<:><:>monthly<:>



.. raw:: html

   <br>

:ref:`Back to Top <index>`
