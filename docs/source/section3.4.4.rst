
.. _section3.4.4:

3.4.4 - Get Web File Information
=====================


.. _GW:

Action Option -**GW** (-**GetWebFile**) (Alias: -**GetWeb**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves Web file records from GDEXDB
  for the specified dataset, optionally filtered by file name.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(GW|GetWebFile) [`Mode Options <mode_>`_]
|         [-(`FN|FieldNames <field_>`_) FieldNameString]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`OB|OrderBy <section5.2_>`_) OrderByPattern]
|         [-(`WF|WebFile <section5.2_>`_) WebFileNames]
|         [-(`WT|WebFileType <section5.2_>`_) WebFileTypes]
|         [-(`FS|FileStatus <section5.2_>`_) WebFileStatus]
|         [-(`FF|FileFlag <section5.2_>`_) FilesOrPaths]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|         [-(`GN|GroupName <section5.2_>`_) GroupNames]
|         [-(`TG|TopGroupIndex <section5.2_>`_) TopGroupIndices]
|         [-(`DE|Description <section5.2_>`_) WebFileDescriptions]
|         [-(`OF|OutputFile <section5.1_>`_) OutputFileName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ options that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4_>`_)
     - formats each column to a uniform fixed width
   * - -(`RG|RecursiveGroup <section4_>`_)
     - gathers files in subgroups recursively for a given group index
   * - -(`RN|RelativeName <section4_>`_)
     - returns file names with paths relative to the Web path of the dataset or group

  Use -`FN <section5.1_>`_ (-FieldNames) to specify which Web file fields to retrieve. Defaults
  to 'FINMTHS'. Use -`FN <section5.1_>`_ ALL for all available fields.

  Valid Web file field names and their corresponding `Info <section5>`_ options:

=  =====  ====================================  ===============================================
   Names  `Info Options <section5>`_            Descriptions                                   
   F      -(`WF|WebFile <section5.2_>`_)        Web file names with relative paths             
   T      -(`WT|WebFileType <section5.2_>`_)    Web file archiving types                       
   C      -(`MC|MD5Checksum <section5.2_>`_)    Web file MD5 Checksum                          
   I      -(`GI|GroupIndex <section5.2_>`_)     group indices for Web files                    
   X      -(`TG|TopGroupIndex <section5.2_>`_)  top group indices for Web files                
   V      -(`VI|VersionIndex <section5.2_>`_)   Version control index                          
   M      -(`AF|ArchiveFormat <section5.2_>`_)  file archive formats                           
   N      -(`DF|DataFormat <section5.2_>`_)     data content formats                           
   O      -(`DO|DisplayOrder <section5.2_>`_)   display order indices                          
   B      -(`QF|QuasarFile <section5.2_>`_)     Quasar backup file names                       
   Q      -(`QT|QuasarType <section5.2_>`_)     Quasar backup file types                       
   L      -(`LC|Location <section5.2_>`_)       Web file storage location flag                 
   H      -(`FS|FileStatus <section5.2_>`_)     Web file archiving status                      
   P      -(`FF|FileFlag <section5.2_>`_)       File type flag, File or Path                   
   S      -(`SZ|Size <section5.2_>`_)           Web file sizes                                 
   J      -(`FD|FileDate <section5.2_>`_)       date data last modified on                     
   K      -(`FT|FileTime <section5.2_>`_)       time data last modified at                     
   A      -(`ML|MetaLink <section5.2_>`_)       a link to content meta at the file level       
   E      -(`TL|ThreddLink <section5.2_>`_)     a link to Thredd Catalog page at the file level
   D      -(`DE|Description <section5.2_>`_)    Web file descriptions                          
=  =====  ====================================  ===============================================

  A dataset number is required unless Web file names are provided. If file
  names match multiple datasets and no dataset number is given, an error prompts
  the specialist to specify one and rerun. Incomplete file paths are expanded
  relative to the dataset Web Home Directory.

  Results can be filtered by archive type (-`WT <section5.2_>`_), group (-`GI <section5.2_>`_ or -`GN <section5.2_>`_), and
  description (-`DE <section5.2_>`_). The -`WF <section5.2_>`_, -`GN <section5.2_>`_, and -`DE <section5.2_>`_ options accept the '%' wildcard.


.. _3.4.4_e10:

**EXAMPLE 10. To retrieve the default Web file fields for d540000, filtered**

  to Data type and file names containing '200':

=  ===================================================================
   dsarch d540000 GW -`WT <section5.2_>`_ D -`WF <section5.2_>`_ %200%
=  ===================================================================

Content of the output:

Dataset<=>d540000
WebFile<:>GroupIndex<:>DataFormat<:>ArchiveFormat<:>WebFileType<:>Size<:>
IMMA_2.4_1998_2000.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1283094016<:>
IMMA_2.4_2001_2002.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1006424064<:>
IMMA_2.4_2003_2004.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1149672960<:>
IMMA_2.4_2005.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>951742976<:>
IMMA_2.4_2006.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1119821824<:>
IMMA_2.4_2007.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>656820224<:>




:ref:`Back to Top <index>`
