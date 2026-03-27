
.. _section3.4.2:

3.4.2 - Get Saved File Information
=====================


.. _GS:

Action Option -**GS** (-**GetSavedFile**) (Alias: -**GetSaved**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves Saved file records from
  GDEXDB for the specified dataset, optionally filtered by file name.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(GS|GetSavedFile) [`Mode Options <mode_>`_]
|         [-(`FN|FieldNames <field_>`_) FieldNameString]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`OB|OrderBy <section5.2_>`_) OrderByPattern]
|         [-(`SF|SavedFile <section5.2_>`_) SavedFileNames]
|         [-(`ST|SavedFileType <section5.2_>`_) SavedFileTypes]
|         [-(`FS|FileStatus <section5.2_>`_) SavedFileStatus]
|         [-(`FF|FileFlag <section5.2_>`_) FilesOrPaths]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`GI|GroupIndex <section5.2_>`_) GroupIndices]
|         [-(`GN|GroupName <section5.2_>`_) GroupNames]
|         [-(`TG|TopGroupIndex <section5.2_>`_) TopGroupIndices]
|         [-(`DE|Description <section5.2_>`_) SavedFileDescriptions]
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
     - returns file names with paths relative to the Saved path of the dataset or group

  Use -`FN <section5.1_>`_ (-FieldNames) to specify which Saved file fields to retrieve. Defaults
  to 'FINMTHS'. Use -`FN <section5.1_>`_ ALL for all available fields.

  Valid Saved file field names and their corresponding `Info <section5>`_ options:

=  =====  ====================================  ====================================
   Names  `Info Options <section5>`_            Descriptions                        
   F      -(`SF|SavedFile <section5.2_>`_)      Saved file names with relative paths
   T      -(`ST|SavedFileType <section5.2_>`_)  Saved file archiving types          
   C      -(`MC|MD5Checksum <section5.2_>`_)    Saved file MD5 Checksum             
   I      -(`GI|GroupIndex <section5.2_>`_)     group indices for Saved files       
   X      -(`TG|TopGroupIndex <section5.2_>`_)  top group indices for Saved files   
   V      -(`VI|VersionIndex <section5.2_>`_)   Version control index               
   N      -(`DF|DataFormat <section5.2_>`_)     data content formats                
   M      -(`AF|ArchiveFormat <section5.2_>`_)  file archive formats                
   O      -(`DO|DisplayOrder <section5.2_>`_)   display order indices               
   B      -(`QF|QuasarFile <section5.2_>`_)     Quasar backup file names            
   Q      -(`QT|QuasarType <section5.2_>`_)     Quasar backup file types            
   L      -(`LC|Location <section5.2_>`_)       Saved file storage location flag    
   H      -(`FS|FileStatus <section5.2_>`_)     Saved file archiving status         
   P      -(`FF|FileFlag <section5.2_>`_)       File type flag, File or Path        
   S      -(`SZ|Size <section5.2_>`_)           Saved file sizes                    
   J      -(`FD|FileDate <section5.2_>`_)       date data last modified on          
   K      -(`FT|FileTime <section5.2_>`_)       time data last modified at          
   D      -(`DE|Description <section5.2_>`_)    Saved file descriptions             
=  =====  ====================================  ====================================

  A dataset number is required unless Saved file names are provided. If file
  names match multiple datasets and no dataset number is given, an error prompts
  the specialist to specify one and rerun. Incomplete file paths are expanded
  relative to the dataset Saved Home Directory.

  Results can be filtered by archive type (-`ST <section5.2_>`_), group (-`GI <section5.2_>`_ or -`GN <section5.2_>`_), and
  description (-`DE <section5.2_>`_). The -`SF <section5.2_>`_, -`GN <section5.2_>`_, and -`DE <section5.2_>`_ options accept the '%' wildcard.




:ref:`Back to Top <index>`
