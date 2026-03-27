
.. _section3.4.6:

3.4.6 - Get Help File Information
=====================


.. _GH:

Action Option -**GH** (-**GetHelpFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

retrieves Help file records (Documents
  and Software) from GDEXDB for the specified dataset, optionally filtered by
  file name.

| **dsarch** [-(`DS|Dataset <section5.1_>`_)] dNNNNNN -(GH|GetHelpFile) [`Mode Options <mode_>`_]
|         [-(`FN|FieldNames <field_>`_) FieldNameString]
|         [-(`ON|OrderNames <section5.1_>`_) OrderNameString]
|         [-(`OB|OrderBy <section5.2_>`_) OrderByPattern]
|         [-(`HF|HelpFile <section5.2_>`_) HelpFileNames]
|         [-(`HT|HelpFileType <section5.2_>`_) HelpFileTypes]
|         [-(`FS|FileStatus <section5.2_>`_) SavedFileStatus]
|         [-(`FF|FileFlag <section5.2_>`_) FilesOrPaths]
|         [-(`LC|Location <section5.2_>`_) StorageLocationFlags]
|         [-(`SR|Source <section5.2_>`_) ContributionSource]
|         [-(`DE|Description <section5.2_>`_) SavedFileDescriptions]
|         [-(`OF|OutputFile <section5.1_>`_) OutputFileName]
|         [-(`DB|Debug <section5.2_>`_) DebugModeInfo]

.. _mode:

  `Mode <section4>`_ option that can be specified for this action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4_>`_)
     - formats each column to a uniform fixed width

  Use -`FN <section5.1_>`_ (-FieldNames) to specify which Help file fields to retrieve. Defaults
  to 'FINMTHSU'. Use -`FN <section5.1_>`_ ALL for all available fields.

  Valid Help file field names and their corresponding `Info <section5>`_ options:

=  =====  ====================================  =================================
   Names  `Info Options <section5>`_            Descriptions                     
   F      -(`HF|HelpFile <section5.2_>`_)       Help file names                  
   N      -(`DF|DataFormat <section5.2_>`_)     file content formats             
   M      -(`AF|ArchiveFormat <section5.2_>`_)  file archive formats             
   O      -(`DO|DisplayOrder <section5.2_>`_)   display order indices            
   T      -(`HT|HelpFileType <section5.2_>`_)   Help file archiving types        
   H      -(`FS|FileStatus <section5.2_>`_)     Help file archiving status       
   P      -(`FF|FileFlag <section5.2_>`_)       File type flag, File or Path     
   L      -(`LC|Location <section5.2_>`_)       Help file storage location flag  
   S      -(`SZ|Size <section5.2_>`_)           Help file sizes                  
   R      -(`SR|Source <section5.2_>`_)         Help file contribution source    
   I      -(`ID|InitialDate <section5.2_>`_)    Date initially Published/Released
   J      -(`FD|FileDate <section5.2_>`_)       date last modified on            
   K      -(`FT|FileTime <section5.2_>`_)       time last modified at            
   U      -(`WU|WebURL <section5.2_>`_)         a full URL for a remote help file
   D      -(`DE|Description <section5.2_>`_)    file descriptions                
=  =====  ====================================  =================================

  A dataset number is required unless Help file names are provided. If file
  names match multiple datasets and no dataset number is given, an error prompts
  the specialist to specify one and rerun.

  Results can be filtered by type (-`HT <section5.2_>`_) and description (-`DE <section5.2_>`_). Both -`HF <section5.2_>`_ and
  -`DE <section5.2_>`_ accept the '%' wildcard.




:ref:`Back to Top <index>`
