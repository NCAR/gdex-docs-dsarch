
.. _section1:

1 - INTRODUCTION
=====================

Program **dsarch** is a comprehensive utility for archiving data onto CISL
Research Data Archive (RDA) Servers; and recording detailed information about
data files, data period, file counts and sizes of a given dataset into Research
Data Archive Database (RDADB). A Digital Object Identifier (DOI) can be
assigned to a dataset to put the dataset under DOI/Version control, and all
the web data files of the dataset are linked to the new DOI/Version Control.
Archived data files for one dataset can be organized into sub-products, called
groups. Data files can be further organized into subgroups. Theoretically there
is no limit to how many levels of subgroups that can be setup. The information
of data files recorded in RDADB can be also retrieved and modified using this
utility program.

A dataset, if not in RDADB yet, can be initiated through Metadata Manager,
`https://dss.ucar.edu/cgi-bin/internal/dssmm <https://dss.ucar.edu/cgi-bin/internal/dssmm>`_. To process data archives, **dsarch**
can perform the following major functions:

#. Setup a dataset, and its groups/subgroups if specified,  in the RDADB to
       make it ready for data archiving
#. Add, update and terminate DOI/Version Controls for a given dataset
#. Archive data files by copying them from working area to the RDA Servers
#. Call **gatherxml** to evaluate file content metadata for the archived files
#. Cross-archive data files by duplicating them between Object Stores and RDA
       Data Disk Servers
#. Save file information of the archived data into RDADB
#. Retrieve dataset/group/file information saved in RDADB
#. Cross-archive data files by duplicating them between Object Stores and RDA
       Data Disk Servers
#. Move data files from one dataset, or even one group, to another; or move
       data files from one location to another
#. Tar a provided file list from one or multiple datasets, and Backup it up
       onto Globus Quasar Server for a backup copy, and optionally another disaster
       backup copy
#. Retore damaged data files from the Quasar backup server
#. Remove files from RDA Servers
#. Auto-restart interrupted dsarch commands recorded in RDADB
#. Regenerate filelist and main webpages on demand after changes made to
       a dataset

A supporting utility program, 'myconvert', was developed to convert and transfer
SCCS metadata (text-based flat files) into RDADB, and another program,
**publish_filelist**, was developed to publish the RDA Server filelists
of datasets to user interfaces on the RDA Web Server. These are complementary
utilities of **dsarch**. Check usages of them for detail help information.

The RDADB dataset flag, -`UD <section5.1.rst#UD>`_ (-UseDSARCH), must be, at least, set to 'Y' for a
dataset before data files can be archived and the associated file information
can be inserted or modified into RDADB by **dsarch**. This flag also controls
publication for file lists: 'P' or 'W' to publish file list for data files on
RDA Server. The published filelists are part of the user interface for
each dataset viewed on the RDA Web Server. Check description of `Action <section3.rst>`_ option
-`SD <section3.1.1.rst>`_ (-SetDataset) and `Info <section5.rst>`_ option -`UD <section5.1.rst#UD>`_ (-UseDSARCH) for details on how to set
this flag properly.

If, after moved, a data file name, including its path, is different from its
original file name, the new file name overrides the original file name,
but the original name is also recorded in RDADB with link to the new data file
name. Both file names are considered to be the same data file when the data
accesses of this file are gathered for usage metrics. Therefore, **dsarch** is
recommended for moving data files, instead of direct moving commands.

Combine another untiliy program, dsquasar, to backup archived data files onto
Globus Quasar Server. The dsquasar helps to identify and create filelists of
un-backed up data files, and save them as input files for dsarch to tar and
back them up.

Some validation procedures are added to prevent DECS specialists from executing
**dsarch** accidentally on a wrong dataset. If an input file is used to hold
option information for processing **dsarch** of a given dataset, the input file
name must start with the dataset number, as in format of 'dsnnn.n.*'; the
wildcard '*' matches one or multiple characters valid for file names. Another
validation is supported to check if a specialist is allowed to execute **dsarch**
on the chosen dataset.  `Action <section3.rst>`_ stops if a specialist is not in the authorized
list, unless a `Mode <section4.rst>`_ option -`MD <section4.rst#MD>`_ (-MyDataset) is present. The option -`MD <section4.rst#MD>`_ tells
**dsarch** to go ahead finish an `Action <section3.rst>`_ forcefully.

For failed data archive actions, (-`AW <section3.4.10.rst>`_|-AS|-`AH <section3.4.11.rst>`_|-AQ), due to storage system downs,
the identical dsarch actions will be retried after the systems are backed up
again. This ability will only be turned on if option -`BP <section5.2.rst#BP>`_ (-d) is present and
the dsarch actions sent into background batch processes, and the related
information is saved in RDADB and

When a DOI/Version control is added to dataset, it can not be removed, although
it can be terminated when the dataset is not active anymore for its data are out
of date. The data filelist of the inactive dataset can still be reconstructed
per user request via the terminated DOI/Version control information. Restrictions
are applied to data files of a dataset that is under DOI/Version control. These
data files can not be moved or deleted, but new data files can be added for
operational datasets. When a data file is archived, normally it can not changed
unless new data are appended to the same data files.

When a dataset is under DOI/Version control, only the Web data files are put
under the version control directly. If there are saved data staged on disks
for internal uses or easy access to the NCAR users, it is responsibility of
the specialist who owns the dataset to maintain them.

In the following sections, general usage of **dsarch** is described first; and
detail descriptions of `Action <section3.rst>`_ options are given next; and then `Mode <section4.rst>`_ and `Info <section5.rst>`_
options are explained in more detail on how to modify and pass information
for `Action <section3.rst>`_ options, respectively. Examples of actions and other options are
interspersed through out the document.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
