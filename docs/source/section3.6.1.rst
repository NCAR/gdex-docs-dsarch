
.. _section3.6.1:

3.6.1 - Regenerate Dataset Webpages
=====================


.. _UW:

Action Option -**UW** (-**UpdateWeb**) :
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

rebuilds the main and filelist webpages for the specified
  dataset so they reflect the current state of GDEXDB.

| **dsarch** [-(:ref:`DS|Dataset <DS>`)] dNNNNNN -(UW|UpdateWeb)
|           [-(:ref:`DB|Debug <DB>`) DebugModeInfo]

  Provide the dataset number to regenerate its web pages.

  **dsarch** automatically bumps a dataset's cache control number whenever it
  writes to GDEXDB, prompting the webpage utility to reload stale cache.
  Changes made through other utilities may not trigger this; use -:ref:`UC <UC>`
  (-UpdateCache) to increment the number manually when needed.




:ref:`Back to Top <index>`
