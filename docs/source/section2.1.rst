
.. _section2.1:

2.1 - Quick Start
=================================

Show the full document, paged through 'more':

.. code-block:: none

   dsarch

Show the description of a single option:

.. code-block:: none

   dsarch -h -AW

Retrieve a dataset record from GDEXDB:

.. code-block:: none

   dsarch d260001 -GD

Set the UseDSARCH flag so the dataset can be archived:

.. code-block:: none

   dsarch d260001 -SD -UD Y

Archive a local file as a Web file:

.. code-block:: none

   dsarch d260001 -AW -LF data.nc

Retrieve the Web file records for a dataset:

.. code-block:: none

   dsarch d260001 -GW



| :ref:`Back to Top <section2.1>`
| :ref:`Back to Table of Contents <index>`
