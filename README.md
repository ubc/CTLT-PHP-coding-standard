CTLT PHP CodeSniffer Coding Standard
========================================

A code standard based on [Symfony 2 coding standards](http://symfony.com/doc/current/contributing/code/standards.html).

Installation
------------

1. Install phpcs:

        pear install PHP_CodeSniffer

2. Find your PEAR directory:

        pear config-show | grep php_dir

3. Copy, symlink or check out this repo and Symfony2 coding standard to the
   phpcs `Standards` directory:

        cd /path/to/pear/PHP/CodeSniffer/Standards
        git clone git://github.com/opensky/Symfony2-coding-standard.git Symfony2
        git clone git://github.com/ubc/CTLT-PHP-coding-standard.git CTLT

4. Set CTLT as your default coding standard:

        phpcs --config-set default_standard CTLT

5. ...

6. Profit!

        cd /path/to/my/project
        phpcs
        phpcs path/to/my/file.php
