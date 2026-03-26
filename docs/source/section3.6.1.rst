
.. _section3.6.1:

3.6.1 - Regenerate Dataset Webpages
=====================


.. _UW:

Action Option -**UW** (-**UpdateWeb**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

regenerates main and filelist webpages to catch the
  changes of dataset/group/file information in RDADB of a given dataset.

| **dsarch** [-(`DS|Dataset <section5.1.rst#DS>`_)] dsnnn.n -(UW|UpdateWeb)
|   [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

  Given a dataset number to refresh its the main and filelist web pages.

  A cache control number of each dataset is increased by 1 each time the
  changes of dataset/group/file information of the dataset are set into RDADB
  by **dsarch**. The new cache number tells webpage utility to refresh the
  cached group and file information of the dataset. Changes made through other
  utilities may not modify this cache control number. Specialists can always
  manually increase this cache number by action -`UC <section3.6.2.rst>`_ (-UpdateCache).



.. raw:: html

   <br>

:ref:`Back to Top <index>`
