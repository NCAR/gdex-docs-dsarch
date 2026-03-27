
.. _section3.4.6:

3.4.6 - Get Help File Information
=====================


.. _GH:

Action Option -**GH** (-**GetHelpFile**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

gets information of Help files, Documents
  and Softwares, for a given dataset and/or specified Help file names. The file
  list can be further specified for given file types, and other
  conditions.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(GH|GetHelpFile) [`Mode Options <#mode>`_]
|   [-(`FN|FieldNames <#field>`_) FieldNameString]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`HF|HelpFile <section5.2.rst#HF>`_) HelpFileNames]
|   [-(`HT|HelpFileType <section5.2.rst#HT>`_) HelpFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) SavedFileStatus]
|   [-(`FF|FileFlag <section5.2.rst#FF>`_) FilesOrPaths]
|   [-(`LC|Location <section5.2.rst#LC>`_) StorageLocationFlags]
|   [-(`SR|Source <section5.2.rst#SR>`_) ContributionSource]
|   [-(`DE|Description <section5.2.rst#DE>`_) SavedFileDescriptions]
|   [(-`OF <section5.1.rst#OF>`_|-OutputFile) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ option that can be specified for getting Help file action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4.rst#FO>`_)
     - format the column output with a same width for all values of a given field

.. _field:

  Use `Info <section5.rst>`_ option -`FN <section5.1.rst#FN>`_ (-FieldNames) to specify what fields of Help files to
  retrieve. It defaults to 'FINMTHSU' if option -`FN <section5.1.rst#FN>`_ is not provided;
  information of all available fields is retrieved if -`FN <section5.1.rst#FN>`_ ALL is given.

  Valid Saved file field names and their corresponding `Info <section5.rst>`_ options:

=  =====  ==========================================  =================================
   Names  `Info Options <section5.rst>`_              Descriptions                     
   F      -(`HF|HelpFile <section5.2.rst#HF>`_)       Help file names                  
   N      -(`DF|DataFormat <section5.2.rst#DF>`_)     file content formats             
   M      -(`AF|ArchiveFormat <section5.2.rst#AF>`_)  file archive formats             
   O      -(`DO|DisplayOrder <section5.2.rst#DO>`_)   display order indices            
   T      -(`HT|HelpFileType <section5.2.rst#HT>`_)   Help file archiving types        
   H      -(`FS|FileStatus <section5.2.rst#FS>`_)     Help file archiving status       
   P      -(`FF|FileFlag <section5.2.rst#FF>`_)       File type flag, File or Path     
   L      -(`LC|Location <section5.2.rst#LC>`_)       Help file storage location flag  
   S      -(`SZ|Size <section5.2.rst#SZ>`_)           Help file sizes                  
   R      -(`SR|Source <section5.2.rst#SR>`_)         Help file contribution source    
   I      -(`ID|InitialDate <section5.2.rst#ID>`_)    Date initially Published/Released
   J      -(`FD|FileDate <section5.2.rst#FD>`_)       date last modified on            
   K      -(`FT|FileTime <section5.2.rst#FT>`_)       time last modified at            
   U      -(`WU <section5.2.rst#WU>`_|WebURL'         a full URL for a remote help file
   D      -(`DE|Description <section5.2.rst#DE>`_)    file descriptions                
=  =====  ==========================================  =================================

  The dataset number per option -`DS <section5.1.rst#DS>`_ (-Dataset) is mandatory unless Help file
  names are provided. An error message is prompted for specialist to pick one
  dataset number and rerun **dsarch** if multiple datasets are identified for
  given Help file information without specified dataset number.

  Help file information can be retrieved for further specified file archive
  types per option -`HT <section5.2.rst#HT>`_ (-HelpFileType), and file descriptions per -`DE <section5.2.rst#DE>`_
  (-Description). `Info <section5.rst>`_ options -`HF <section5.2.rst#HF>`_ and -`DE <section5.2.rst#DE>`_ accept wildcard inputs of '%'
  for matching any number of characters.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
