
.. _section3.4.4:

3.4.4 - Get Web File Information
=====================


.. _GW:

Action Option -**GW** (-**GetWebFile**) (Alias: -**GetWeb**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

gets information of data files on RDA
  Server for a given dataset and/or specified Web file names. The list of data
  files can be further specified for given group indices, file archive types,
  and file descriptions.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(GW|GetWebFile) [`Mode Options <#mode>`_]
|   [-(`FN|FieldNames <#field>`_) FieldNameString]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`WF|WebFile <section5.2.rst#WF>`_) WebFileNames]
|   [-(`WT|WebFileType <section5.2.rst#WT>`_) WebFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) WebFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`GN|GroupName <section5.2.rst#GN>`_) GroupNames]
|   [-(`TG|TopGroupIndex <section5.2.rst#TG>`_) TopGroupIndices]
|   [-(`DE|Description <section5.2.rst#DE>`_) WebFileDescriptions]
|   [(-`OF <section5.1.rst#OF>`_|-OutputFile) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for getting Web file action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4.rst#FO>`_)
     - format the column output with a same width for all values of a given field
   * - -(`RG|REcursiveGroup <section4.rst#RG>`_)
     - gather files in subgroups recursively for given group index
   * - -(`RN|RelativeName <section4.rst#RN>`_)
     - retrieves Web file names with paths relative to saved Web paths for groups or dataset

.. _field:

  Use `Info <section5.rst>`_ option -`FN <section5.1.rst#FN>`_ (-FieldNames) to specify what fields of file on RDA
  Server to retrieve. It defaults to 'FINMTHS' if option -`FN <section5.1.rst#FN>`_ is not provided;
  information of all available fields is retrieved if -`FN <section5.1.rst#FN>`_ ALL is given.

  Valid Web file field names and their corresponding `Info <section5.rst>`_ options:

=  =====  ==========================================  ===============================================
   Names  `Info Options <section5.rst>`_              Descriptions                                   
   F      -(`WF|WebFile <section5.2.rst#WF>`_)        Web file names with relative paths             
   T      -(`WT|WebFileType <section5.2.rst#WT>`_)    Web file archiving types                       
   C      -(`MC|MD5Checksum <section5.2.rst#MC>`_)    Web file MD5 Checksum                          
   I      -(`GI|GroupIndex <section5.2.rst#GI>`_)     group indices for Web files                    
   X      -(`TG|TopGroupIndex <section5.2.rst#TG>`_)  top group indices for Web files                
   V      -(`VI|VersionIndex <section5.2.rst#VI>`_)   Version control index                          
   M      -(`AF|ArchiveFormat <section5.2.rst#AF>`_)  file archive formats                           
   N      -(`DF|DataFormat <section5.2.rst#DF>`_)     data content formats                           
   O      -(`DO|DisplayOrder <section5.2.rst#DO>`_)   display order indices                          
   B      -(`QF|QuasarFile <section5.2.rst#QF>`_)     Quasar backup file names                       
   Q      -(`QT|QuasarType <section5.2.rst#QT>`_)     Quasar backyp fie types                        
   L      -(`LC|Location <section5.2.rst#LC>`_)       Web file storage location flag                 
   H      -(`FS|FileStatus <section5.2.rst#FS>`_)     Web file archiving status                      
   P      -(`FF|FileFlag <section5.2.rst#FF>`_)       File type flag, File or Path                   
   S      -(`SZ|Size <section5.2.rst#SZ>`_)           Web file sizes                                 
   J      -(`FD|FileDate <section5.2.rst#FD>`_)       date data last modified on                     
   K      -(`FT|FileTime <section5.2.rst#FT>`_)       time data last modified at                     
   A      -(`ML|MetaLink <section5.2.rst#ML>`_)       a link to content meta at the file level       
   E      -(`TL|ThreddLink <section5.2.rst#TL>`_)     a link to Thredd Catalog page at the file level
   D      -(`DE|Description <section5.2.rst#DE>`_)    Web file descriptions                          
=  =====  ==========================================  ===============================================

  The dataset number per option -`DS <section5.1.rst#DS>`_ (-Dataset) is mandatory unless Web file
  names are provided. An error message is prompted for specialist to pick one
  dataset number and rerun **dsarch** if multiple datasets are identified for
  given Web file information without specified dataset number. Web file names
  are expanded automatically to include full paths relative to the dataset Web
  Home Directories if the file names are given without or with incomplete paths.

  Web file information can be retrieved for further specified file archive
  types per option -`WT <section5.2.rst#WT>`_ (-WebFileType), groups per option -`GI <section5.2.rst#GI>`_ (-GroupIndex) or
  -`GN <section5.2.rst#GN>`_ (-GroupName), and Web file descriptions per -`DE <section5.2.rst#DE>`_ (-Description). `Info <section5.rst>`_
  options -`WF <section5.2.rst#WF>`_, -`GN <section5.2.rst#GN>`_ and -`DE <section5.2.rst#DE>`_ accept wildcard inputs of '%' for matching any number
  of characters.


.. _e10:

**EXAMPLE 10. **

Get The Web File Information Of D540000 For Default Fields;
  for Data type and wildcard matching '200' in Web file names

  dsarch d540000 GW -`WT <section5.2.rst#WT>`_ D -`WF <section5.2.rst#WF>`_ %200%

Content of the output:

Dataset<=>d540000
WebFile<:>GroupIndex<:>DataFormat<:>ArchiveFormat<:>WebFileType<:>Size<:>
IMMA_2.4_1998_2000.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1283094016<:>
IMMA_2.4_2001_2002.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1006424064<:>
IMMA_2.4_2003_2004.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1149672960<:>
IMMA_2.4_2005.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>951742976<:>
IMMA_2.4_2006.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>1119821824<:>
IMMA_2.4_2007.tar<:>37<:>IMMA<:>Z.TAR<:>D<:>656820224<:>



.. raw:: html

   <br>

:ref:`Back to Top <index>`
