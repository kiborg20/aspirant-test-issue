==================================
Rule ``single_line_comment_style``
==================================

Single-line comments and multi-line comments with only one line of actual
content should use the ``//`` syntax.

Configuration
-------------

``comment_types``
~~~~~~~~~~~~~~~~~

List of comment types to fix

Allowed values: a subset of ``['asterisk', 'hash']``

Default value: ``['asterisk', 'hash']``

Examples
--------

Example #1
~~~~~~~~~~

*Default* configuration.

.. code-block:: diff

   --- Original
   +++ New
   @@ -1,8 +1,8 @@
    <?php
   -/* asterisk comment */
   +// asterisk comment
    $a = 1;

   -# hash comment
   +// hash comment
    $b = 2;

    /*

Example #2
~~~~~~~~~~

With configuration: ``['comment_types' => ['asterisk']]``.

.. code-block:: diff

   --- Original
   +++ New
   @@ -1,10 +1,8 @@
    <?php
   -/* first comment */
   +// first comment
    $a = 1;

   -/*
   - * second comment
   - */
   +// second comment
    $b = 2;

    /*

Example #3
~~~~~~~~~~

With configuration: ``['comment_types' => ['hash']]``.

.. code-block:: diff

   --- Original
   +++ New
   @@ -1 +1 @@
   -<?php # comment
   +<?php // comment

Rule sets
---------

The rule is part of the following rule sets:

@PhpCsFixer
  Using the `@PhpCsFixer <./../../ruleSets/PhpCsFixer.rst>`_ rule set will enable the ``single_line_comment_style`` rule with the default config.

@Symfony
  Using the `@Symfony <./../../ruleSets/Symfony.rst>`_ rule set will enable the ``single_line_comment_style`` rule with the config below:

  ``['comment_types' => ['hash']]``
