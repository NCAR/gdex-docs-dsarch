
.. _section3.4.2:

3.4.2 - Get Saved File Information
=====================


.. _GS:

Action Option -**GS** (-**GetSavedFile**) (Alias: -**GetSaved**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

gets information of data files on Saved
  Server for a given dataset and/or specified Saved file names. The list of data
  files can be further specified for given group indices, file archive types,
  and other conditions.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(GS|GetSavedFile) [`Mode Options <#mode>`_]
|   [-(`FN|FieldNames <#field>`_) FieldNameString]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`SF|SavedFile <section5.2.rst#SF>`_) SavedFileNames]
|   [-(`ST|SavedFileType <section5.2.rst#ST>`_) SavedFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) SavedFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`GI|GroupIndex <section5.2.rst#GI>`_) GroupIndices]
|   [-(`GN|GroupName <section5.2.rst#GN>`_) GroupNames]
|   [-(`TG|TopGroupIndex <section5.2.rst#TG>`_) TopGroupIndices]
|   [-(`DE|Description <section5.2.rst#DE>`_) SavedFileDescriptions]
|   [(-`OF <section5.1.rst#OF>`_|-OutputFile) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for getting Saved file action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4.rst#FO>`_)
     - format the column output with a same width for all values of a given field
   * - -(`RG|REcursiveGroup <section4.rst#RG>`_)
     - gather files in subgroups recursively for given group index
   * - -(`RN|RelativeName <section4.rst#RN>`_)
     - retrieves Saved file names with paths relative to saved paths for groups or dataset

.. _field:

  Use `Info <section5.rst>`_ option -`FN <section5.1.rst#FN>`_ (-FieldNames) to specify what fields of file on Saved
  Server to retrieve. It defaults to 'FINMTHS' if option -`FN <section5.1.rst#FN>`_ is not provided;
  information of all available fields is retrieved if -`FN <section5.1.rst#FN>`_ ALL is given.

  Valid Saved file field names and their corresponding `Info <section5.rst>`_ options:

=  =====  ==========================================  ====================================
   Names  `Info Options <section5.rst>`_              Descriptions                        
   F      -(`SF|SavedFile <section5.2.rst#SF>`_)      Saved file names with relative paths
   T      -(`ST|SavedFileType <section5.2.rst#ST>`_)  Saved file archiving types          
   C      -(`MC|MD5Checksum <section5.2.rst#MC>`_)    Saved file MD5 Checksum             
   I      -(`GI|GroupIndex <section5.2.rst#GI>`_)     group indices for Saved files       
   X      -(`TG|TopGroupIndex <section5.2.rst#TG>`_)  top group indices for Saved files   
   V      -(`VI|VersionIndex <section5.2.rst#VI>`_)   Version control index               
   N      -(`DF|DataFormat <section5.2.rst#DF>`_)     data content formats                
   M      -(`AF|ArchiveFormat <section5.2.rst#AF>`_)  file archive formats                
   O      -(`DO|DisplayOrder <section5.2.rst#DO>`_)   display order indices               
   B      -(`QF|QuasarFile <section5.2.rst#QF>`_)     Quasar backup file names            
   Q      -(`QT|QuasarType <section5.2.rst#QT>`_)     Quasar backyp file types            
   L      -(`LC|Location <section5.2.rst#LC>`_)       Saved file storage location flag    
   H      -(`FS|FileStatus <section5.2.rst#FS>`_)     Saved file archiving status         
   P      -(`FF|FileFlag <section5.2.rst#FF>`_)       File type flag, File or Path        
   S      -(`SZ|Size <section5.2.rst#SZ>`_)           Saved file sizes                    
   J      -(`FD|FileDate <section5.2.rst#FD>`_)       date data last modified on          
   K      -(`FT|FileTime <section5.2.rst#FT>`_)       time data last modified at          
   D      -(`DE|Description <section5.2.rst#DE>`_)    Saved file descriptions             
=  =====  ==========================================  ====================================

  The dataset number per option -`DS <section5.1.rst#DS>`_ (-Dataset) is mandatory unless Saved file
  names are provided. An error message is prompted for specialist to pick one
  dataset number and rerun **dsarch** if multiple datasets are identified for
  given Saved file information without specified dataset number. Saved file names
  are expanded automatically to include full paths relative to the dataset Saved
  Home Directories if the file names are given without or with incomplete paths.

  Saved file information can be retrieved for further specified file archive
  types per option -`ST <section5.2.rst#ST>`_ (-SavedFileType), groups per option -`GI <section5.2.rst#GI>`_ (-GroupIndex) or
  -`GN <section5.2.rst#GN>`_ (-GroupName), and Saved file descriptions per -`DE <section5.2.rst#DE>`_ (-Description). `Info <section5.rst>`_
  options -`SF <section5.2.rst#SF>`_, -`GN <section5.2.rst#GN>`_ and -`DE <section5.2.rst#DE>`_ accept wildcard inputs of '%' for matching any number
  of characters.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
