
.. _section1:

1 - INTRODUCTION
=================================

**dsarch** is the primary tool for archiving geoscience data onto CISL's
Geoscience Data Exchange (GDEX) Servers. It records metadata for every
dataset — file names, data periods, file counts, and sizes — in the
Geoscience Data Exchange Database (GDEXDB). Datasets can be placed under
DOI/Version control by assigning a Digital Object Identifier (DOI) that
links all web data files to a specific version for citation and long-term
reference. Files can be organized into nested sub-products called groups.
Any metadata stored in GDEXDB can also be retrieved or updated through
**dsarch**.

A few terms used throughout this document:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - GDEX
     - Geoscience Data Exchange, NCAR's data publication platform
   * - GDEXDB
     - the metadata database backing GDEX
   * - Specialist
     - an authorized owner who manages a dataset
   * - dNNNNNN
     - a dataset number; six digits prefixed with 'd' (e.g., d260001)
   * - Group
     - a named sub-product within a dataset; groups can be nested
   * - Saved file
     - an archived file kept for internal use or NCAR users
   * - Web file
     - an archived file published on the GDEX Web Server
   * - Help file
     - documentation or software file (Document or Software)
   * - Quasar
     - the Globus Quasar Server used for long-term tape backup

Before using **dsarch**, register the dataset in GDEXDB through Metadata
Manager (https://gdex.ucar.edu/metaman/). Once registered, **dsarch** can
perform the following major functions:

* Set up a dataset and its groups/subgroups in GDEXDB to prepare it for data archiving
* Add, update, and terminate DOI/Version controls for a given dataset
* Archive data files by copying them from the working area to GDEX Servers
* Call **gatherxml** to evaluate file content metadata for archived files
* Cross-archive data files by duplicating them between bOreas and GDEX Data Disk Servers
* Save file information for archived data into GDEXDB
* Retrieve dataset, group, and file information stored in GDEXDB
* Move data files from one dataset or group to another, or to a different location within the same dataset
* Tar file lists from one or more datasets and back them up onto the Globus Quasar Server, with an optional disaster recovery copy
* Restore damaged data files from the Quasar backup server
* Remove files from GDEX Servers
* Automatically resume interrupted **dsarch** commands using records in GDEXDB
* Regenerate filelist and main webpages on demand after dataset changes

The dataset flag :ref:`-UD <UD>` (-UseDSARCH) must be set to at least 'Y' before
**dsarch** can archive files or write to GDEXDB. This flag also controls
file list publication: setting it to 'P' or 'W' publishes file lists for
GDEX Server data files, making them visible in the dataset's user
interface on the GDEX Web Server. See the :ref:`-SD <SD>` (-SetDataset) action and
the :ref:`-UD <UD>` (-UseDSARCH) option for details.

When a file is moved and its name or path changes, **dsarch** records the
new name as the primary entry in GDEXDB and retains the original as a
linked alias. Both names resolve to the same file for usage tracking.
Always use **dsarch** — not system move commands — to move data files, so
that GDEXDB stays accurate.

Use the companion utility 'dsquasar' to back up archived data files to
the Globus Quasar Server. 'dsquasar' finds files not yet backed up,
assembles input file lists (targeting 1-3 GB per list), and calls
**dsarch** to package and upload them as tar files to the Quasar server.

**dsarch** includes safeguards to prevent accidental operations on the
wrong dataset. Input files must be named starting with the dataset
number in the format 'dNNNNNN.*', where '*' matches one or more valid
filename characters. **dsarch** also verifies that the specialist running
it is an authorized owner of the dataset; if not, execution stops —
unless :ref:`Mode option <section4>` :ref:`-MD <MD>` (-MyDataset) is supplied, which overrides the
ownership check.

If an archive action (:ref:`-AW <AW>`, :ref:`-AS <AS>`, :ref:`-AH <AH>`, :ref:`-AQ <AQ>`) fails due to a storage system
outage, **dsarch** automatically retries it once the system recovers.
Retry behavior is enabled only when option :ref:`-BP <BP>` (-d) is used to submit
the action as a background batch process; the retry state is tracked in
GDEXDB.

Once added, a DOI/Version control record cannot be removed, but it can
be terminated when a dataset is retired and its data are no longer
current. Even after termination, the file list can be reconstructed from
the retained DOI records. Files under DOI/Version control are locked —
they cannot be moved or deleted — though new files may still be added to
operational datasets. Archived data files are also immutable unless new
data are appended to them.

Only Web data files are placed under DOI/Version control. Saved data
staged on disk for internal use or NCAR user access is not version-
controlled and remains the responsibility of the dataset owner.

This document first covers general **dsarch** usage, then describes each
:ref:`Action option <section3>` in detail, followed by :ref:`Mode <section4>` and Information (:ref:`Info <section5>` for
short) options. Examples are provided throughout each section.



| :ref:`Back to Top <section1>`
| :ref:`Back to Table of Contents <index>`
