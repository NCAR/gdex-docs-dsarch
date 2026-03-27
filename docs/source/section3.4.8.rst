
.. _section3.4.8:

3.4.8 - Get Quasar File Information
=====================


.. _GQ:

Action Option -**GQ** (-**GetQuasarFile**) (Aliases: -**GetQuasar**, -**GetBackupFile**, -**GetBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves Quasar backup file records
  from GDEXDB for the specified dataset, optionally filtered by file name.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(GQ|GetQuasarFile) [`Mode Options <mode_>`_]
|         [-(`FN|FieldNames <field_>`_) FieldNameString]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`OB|OrderBy <section5.2_>`_) OrderByPattern]
|         [-(`QF|QuasarFile <section5.2_>`_) QuasarFileNames]
|         [-(`QT|QuasarFileType <section5.2_>`_) QuasarFileTypes]
|         [-(`FS|FileStatus <section5.2_>`_) QuasarFileStatus]
|         [-(`DE|Description <section5.2_>`_) QuasarFileDescriptions]
|         [-(`OF|OutputFile <section5.1_>`_) OutputFileName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ option that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4_>`_)
     - formats each column to a uniform fixed width

  Use -`FN <section5.1_>`_ (-FieldNames) to specify which Quasar file fields to retrieve. Defaults
  to 'FNMTHS'. Use -`FN <section5.1_>`_ ALL for all available fields.

  Valid Quasar file field names and their corresponding `Info <section5>`_ options:

=  =====  =====================================  =====================================
   Names  `Info Options <section5>`_             Descriptions                         
   F      -(`QF|QuasarFile <section5.2_>`_)      Quasar file names with relative paths
   T      -(`QT|QuasarFileType <section5.2_>`_)  Quasar file archiving types          
   C      -(`MC|MD5Checksum <section5.2_>`_)     Saved file MD5 Checksum              
   N      -(`DF|DataFormat <section5.2_>`_)      data content formats                 
   M      -(`AF|ArchiveFormat <section5.2_>`_)   file archive formats                 
   O      -(`DO|DisplayOrder <section5.2_>`_)    display order indices                
   B      -(`QF|QuasarFile <section5.2_>`_)      Quasar backup file names             
   Q      -(`QT|QuasarType <section5.2_>`_)      Quasar backup file types             
   H      -(`FS|FileStatus <section5.2_>`_)      Quasar file archiving status         
   S      -(`SZ|Size <section5.2_>`_)            Quasar file sizes                    
   J      -(`FD|FileDate <section5.2_>`_)        date data last modified on           
   K      -(`FT|FileTime <section5.2_>`_)        time data last modified at           
   D      -(`DE|Description <section5.2_>`_)     Quasar file descriptions             
=  =====  =====================================  =====================================

  A dataset number is required unless Quasar file names are provided. If file
  names match multiple datasets and no dataset number is given, an error prompts
  the specialist to specify one and rerun. Incomplete file paths are expanded
  relative to the dataset Home Directory.

  Results can be filtered by archive type (-`QT <section5.2_>`_) and description (-`DE <section5.2_>`_). Both
  -`QF <section5.2_>`_ and -`DE <section5.2_>`_ accept the '%' wildcard.




:ref:`Back to Top <index>`
