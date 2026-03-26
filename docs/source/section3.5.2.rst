
.. _section3.5.2:

3.5.2 - Set All Information
=====================


.. _SA:

Action Option -**SA** (-**SetALL**) :
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

creates and modifies dataset, group and Saved/Web/Help/Quasar
  file information into RDADB for a given dataset number. This is a comprehensive
  action, combining all four Set Actions, -`SD <section3.1.1.rst>`_ (-SetDataset), -`SG <section3.3.1.rst>`_ (-SetGroup), -`SS <section3.4.1.rst>`_
  (-SetSavedFile), -`SW <section3.4.3.rst>`_ (-SetWebFile), -`SH <section3.4.5.rst>`_ (-SetHelpFile), and -`SQ <section3.4.7.rst>`_ (-SetQuasarFile).

  dsarch  -(`SA|SetAll <#SA>`_) [`Mode Options <section4.rst>`_]
         [-(`LN|LoginName <section5.1.rst#LN>`_) LoginAccountName]
          -(`IF|InputFile <section5.2.rst#IF>`_) Input Files
         [-(`DB|Debug <section5.2.rst#DB>`_) DebugModeInfo]

  ALL `Mode <section4.rst>`_ options that can be applied to the Set Actions, -`SD <section3.1.1.rst>`_, -`SG <section3.3.1.rst>`_, -`SW <section3.4.3.rst>`_, -`SH <section3.4.5.rst>`_
  and -`SQ <section3.4.7.rst>`_ can be specified for this action. At least one input file is need to
  execute this action since section headers need to be specified in an input file.
  One way of creating an input file is to get one per action -`GA <section3.5.1.rst>`_ (-GetALL) for a
  dataset. The output file can then be edited and used as an input file to set
  all information of the dataset back to RDADB.



.. raw:: html

   <br>

:ref:`Back to Top <index>`
