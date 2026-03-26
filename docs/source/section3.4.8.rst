
.. _section3.4.8:

3.4.8 - Get Quasar File Information
=====================


.. _GQ:

Action Option -**GQ** (-**GetQuasarFile**) (Aliases: -**GetQuasar**, -**GetBackupFile**, -**GetBackup**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

gets information of backup files on
  Quasar Server for a given dataset and/or specified Quasar file names. The file
  list can be further specified for file archive types, and other conditions.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(GQ|GetQuasarFile) [`Mode Options <#mode>`_]
|   [-(`FN|FieldNames <#field>`_) FieldNameString]
|   [-(`ON|OrderNames <section5.1.rst#ON>`_) OrderNameString]
|   [-(`OB|OrderBy <section5.2.rst#OB>`_) OrderByPattern]
|   [-(`QF|QuasarFile <section5.2.rst#QF>`_) QuasarFileNames]
|   [-(`QT|QuasarFileType <section5.2.rst#QT>`_) QuasarFileTypes]
|   [-(`FS|FileStatus <section5.2.rst#FS>`_) QuasarFileStatus]
|   [-(`DE|Description <section5.2.rst#DE>`_) QuasarFileDescriptions]
|   [(-`OF <section5.1.rst#OF>`_|-OutputFile) OutputFileName]
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

.. _mode:

  `Mode <section4.rst>`_ options that can be specified for getting Saved file action:

.. list-table::
   :widths: auto

   * - -(`FO|FormatOutput <section4.rst#FO>`_)
     - format the column output with a same width for all values of a given field

.. _field:

  Use `Info <section5.rst>`_ option -`FN <section5.1.rst#FN>`_ (-FieldNames) to specify what fields of file on Saved
  Server to retrieve. It defaults to 'FNMTHS' if option -`FN <section5.1.rst#FN>`_ is not provided;
  information of all available fields is retrieved if -`FN <section5.1.rst#FN>`_ ALL is given.

  Valid Saved file field names and their corresponding `Info <section5.rst>`_ options:

=  =====  ===========================================  =====================================
   Names  `Info Options <section5.rst>`_               Descriptions                         
   F      -(`QF|QuasarFile <section5.2.rst#QF>`_)      Quasar file names with relative paths
   T      -(`QT|QuasarFileType <section5.2.rst#QT>`_)  Quasar file archiving types          
   C      -(`MC|MD5Checksum <section5.2.rst#MC>`_)     Saved file MD5 Checksum              
   N      -(`DF|DataFormat <section5.2.rst#DF>`_)      data content formats                 
   M      -(`AF|ArchiveFormat <section5.2.rst#AF>`_)   file archive formats                 
   O      -(`DO|DisplayOrder <section5.2.rst#DO>`_)    display order indices                
   B      -(`QF|QuasarFile <section5.2.rst#QF>`_)      Quasar backup file names             
   Q      -(`QT|QuasarType <section5.2.rst#QT>`_)      Quasar backyp fie types              
   H      -(`FS|FileStatus <section5.2.rst#FS>`_)      Quasar file archiving status         
   S      -(`SZ|Size <section5.2.rst#SZ>`_)            Quasar file sizes                    
   J      -(`FD|FileDate <section5.2.rst#FD>`_)        date data last modified on           
   K      -(`FT|FileTime <section5.2.rst#FT>`_)        time data last modified at           
   D      -(`DE|Description <section5.2.rst#DE>`_)     Quasar file descriptions             
=  =====  ===========================================  =====================================

  The dataset number per option -`DS <section5.1.rst#DS>`_ (-Dataset) is mandatory unless Quasar file
  names are provided. An error message is prompted for specialist to pick one
  dataset number and rerun **dsarch** if multiple datasets are identified for
  given Quasar file information without specified dataset number. Quasar file
  names are expanded automatically to include full paths relative to the dataset
  Home Directories if the file names are given without or with incomplete paths.

  Quasar file information can be retrieved for further specified file archive
  types per option -`QT <section5.2.rst#QT>`_ (-QuasarFileType) and Quasar file descriptions per -`DE <section5.2.rst#DE>`_
  (-Description). `Info <section5.rst>`_ options -`QF <section5.2.rst#QF>`_ and -`DE <section5.2.rst#DE>`_ accept wildcard inputs of '%' for
  matching any number of characters.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
