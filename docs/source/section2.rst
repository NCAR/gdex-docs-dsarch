
.. _section2:

2 - GENERAL DSARCH USAGE
=================================

| **dsarch** [[:ref:`-(DS|Dataset) <DS>`] dNNNNNN] [:ref:`Action Option <section3>`] [:ref:`Mode Options <section4>`] [:ref:`Info Options <section5>`]
|        or
| **dsarch** [:ref:`-(IF|InputFile) <IF>`] InputFileNames

Brackets [] indicate optional elements. A pipe '|' within parentheses,
as in (A|B), means either A or B may be used. Options fall into three
categories:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - :ref:`Action options <section3>`
     - specify the task to execute
   * - :ref:`Mode options <section4>`
     - modify how an action behaves
   * - :ref:`Info options <section5>`
     - supply values to the action

Options may be given in short or long form (e.g., :ref:`-DS <DS>` or -Dataset). Some
options have alias names; for example, -UseRDADB is an alias for :ref:`-UD <UD>`
(-UseDSARCH). Option names are case-insensitive, but values following
:ref:`Info options <section5>` are case-sensitive.

Option :ref:`-DS <DS>` specifies the dataset number. It is listed separately because
most actions require it. When :ref:`-DS <DS>` is the first argument after **dsarch**,
the option name itself may be omitted — just supply the dataset number
directly.

Specify exactly one :ref:`Action option <section3>` per **dsarch** invocation. Each action
has its own set of required and optional :ref:`Info options <section5>`, and may accept
specific :ref:`Mode options <section4>` that adjust its behavior.

All options except :ref:`-IF <IF>` (-InputFile) may be given either on the command
line or in input files. Input file names are specified via :ref:`-IF <IF>` and can
only be supplied on the command line. See the :ref:`-IF <IF>` option description for
details on how to format options in input files. One or more input files
may be combined with command-line options. The :ref:`-IF <IF>` option name itself
may be omitted when a single input file is given on the command line and
all action and option information is contained within that file.

:ref:`Info options <section5>` used with GET actions serve as query filters. Four special
characters enable more precise filtering — they must be quoted or
escaped on the command line to prevent shell interpretation:

.. list-table::
   :widths: auto
   :header-rows: 0

   * - '!'
     - exclude matches; must appear immediately after the option name (may need escaping as '\!' in some shells due to history expansion)
   * - '<'
     - less-than comparison on the following value
   * - '>'
     - greater-than comparison on the following value
   * - '<>'
     - range between two values

Combining '!' and '<' as "'!' '<' OptionValue" expresses a 'greater than
or equal to OptionValue' condition.

The description of an individual option is shown when **dsarch** is run as

| **dsarch** [Option] -(h|help) [Option]

The description is shown for the option placed either before or after
-(h|help). If no option is given, or **dsarch** is run without arguments,
the full document is displayed using the UNIX 'more' utility. A hard
copy of this document can be printed from the saved file, dsarch.usg,
in the rda_python_dsarch Python package.



| :ref:`Back to Top <section2>`
| :ref:`Back to Table of Contents <index>`
