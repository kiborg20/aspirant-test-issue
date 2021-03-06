=====================================
Rule ``phpdoc_return_self_reference``
=====================================

The type of ``@return`` annotations of methods returning a reference to itself
must the configured one.

Configuration
-------------

``replacements``
~~~~~~~~~~~~~~~~

Mapping between replaced return types with new ones.

Allowed types: ``array``

Default value: ``['this' => '$this', '@this' => '$this', '$self' => 'self', '@self' => 'self', '$static' => 'static', '@static' => 'static']``

Examples
--------

Example #1
~~~~~~~~~~

*Default* configuration.

.. code-block:: diff

   --- Original
   +++ New
   @@ -2,7 +2,7 @@
    class Sample
    {
        /**
   -     * @return this
   +     * @return $this
         */
        public function test1()
        {
   @@ -10,7 +10,7 @@
        }

        /**
   -     * @return $self
   +     * @return self
         */
        public function test2()
        {

Example #2
~~~~~~~~~~

With configuration: ``['replacements' => ['this' => 'self']]``.

.. code-block:: diff

   --- Original
   +++ New
   @@ -2,7 +2,7 @@
    class Sample
    {
        /**
   -     * @return this
   +     * @return self
         */
        public function test1()
        {

Rule sets
---------

The rule is part of the following rule sets:

@PhpCsFixer
  Using the `@PhpCsFixer <./../../ruleSets/PhpCsFixer.rst>`_ rule set will enable the ``phpdoc_return_self_reference`` rule with the default config.

@Symfony
  Using the `@Symfony <./../../ruleSets/Symfony.rst>`_ rule set will enable the ``phpdoc_return_self_reference`` rule with the default config.
