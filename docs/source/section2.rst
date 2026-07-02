
.. _section2:

2 - GENERAL DSARCH USAGE
=================================

| **dsarch** [[:ref:`-(DS|Dataset) <DS>`] dNNNNNN] [:ref:`Action Option <section3>`] [:ref:`Mode Options <section4>`] [:ref:`Info Options <section5>`]
|        or
| **dsarch** [:ref:`-(IF|InputFile) <IF>`] InputFileNames

Notation:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - []
     - the enclosed element is optional.
   * - (A|B)
     - either A or B may be used (a short form and a long form).
   * - <OPT>
     - OPT is an option name. Names are case-insensitive; values are not.

Every dsarch invocation has at most one :ref:`Action option <section3>`, which selects the
task to perform. :ref:`Mode options <section4>` change how the chosen action behaves. :ref:`Info <section5>`
options carry the data the action needs (file names, group indices, dates,
etc.). Each action documents which :ref:`Info options <section5>` are required and which are
optional.

Option :ref:`-DS <DS>` (-Dataset) supplies the dataset number. It is listed separately
because most actions require it. When :ref:`-DS <DS>` is the first argument after
**dsarch**, the option name itself may be omitted — just supply the dataset
number directly.

Many options have an alias for convenience; for example, -UseRDADB is an
alias for :ref:`-UD <UD>` (-UseDSARCH). Both short and long forms are accepted, and
aliases are noted with each option.

.. toctree::
   :maxdepth: 2
   :caption: Table of Contents

   section2.1
   section2.2
   section2.3
   section2.4



| :ref:`Back to Top <section2>`
| :ref:`Back to Table of Contents <index>`
