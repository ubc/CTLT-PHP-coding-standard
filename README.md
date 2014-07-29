CTLT PHP CodeSniffer Coding Standard
========================================

A code standard based on [Symfony 2 coding standards](http://symfony.com/doc/current/contributing/code/standards.html).

Installation (Composer)
-----------------------

1. [Install composer](https://getcomposer.org/download/)
2. Add the dependency to composer.json:

    ```json
    {
        "require-dev": {
            "ubc/ctlt-coding-standard": "~1.0",
        }
    }
    ```
3. Install dependencies

    composer update

4. Use it

    phpcs --standard=vendor/ubc/ctlt-coding-standard/ruleset.xml --runtime-set installed_paths vendor/m6web/symfony2-coding-standard src/*

Or add the following Phing task:

    <target name="phpcs"
        description="Find coding standard violations using PHP_CodeSniffer and print human readable output. Intended for usage on the command line before committing.">
        <phpcodesniffer standard="${vendordir}/ubc/ctlt-coding-standard/ruleset.xml">
            <config name="installed_paths" value="${vendordir}/m6web/symfony2-coding-standard"/>
            <fileset dir="${sourcedir}">
                <include name="**/*.php" />
            </fileset>
        </phpcodesniffer>
    </target>

Installation (Pear)
-------------------

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
