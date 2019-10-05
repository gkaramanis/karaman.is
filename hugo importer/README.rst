###############
ExitWP for Hugo
###############

This is a port of Thomas Frössman's ExitWP tool (for Jekyll).

You can find also a howto and background information here on my website: https://arjan.wooning.cz/conversion-tools-from-wordpress-to-hugo/#final-solution-exitwp-for-hugo


Exitwp is tool for making migration from one or more wordpress blogs to the `hugo blog engine <https://gohugo.io/>`_ as easy as possible.

By default it will try to convert as much information as possible from wordpress but can also be told to filter the amount of data it converts.

The latest version of these docs should always be available at https://github.com/wooni005/exitwp-for-hugo

Getting started
===============
 * `Download <https://github.com/wooni005/exitwp-for-hugo/zipball/master>`_ or clone using ``git clone https://github.com/wooni005/exitwp-for-hugo.git``
 * Export one or more wordpress blogs using the wordpress exporter under tools/export in wordpress admin.
 * Put all wordpress xml files in the ``wordpress-xml`` directory
 * Special note for Wordpress 3.1, you need to add a missing namespace in rss tag : ``xmlns:atom="http://www.w3.org/2005/Atom"``
 * Run xmllint on your export file and fix errors if there are.
 * Run the converter by typing ``./exitwp.py`` in the console from the directory of the unzipped archive
 * You should now have all the blogs converted into separate directories under the ``build`` directory

Runtime dependencies
====================
 * `Python <http://python.org/>`_ 2.6, 2.7, ???
 * `html2text <http://www.aaronsw.com/2002/html2text/>`_ :  converts HTML to markdown (python)
 * `PyYAML <http://pyyaml.org/wiki/PyYAML>`_ : Reading configuration files and writing YAML headers (python)
 * `Beautiful soup <http://www.crummy.com/software/BeautifulSoup/>`_ : Parsing and downloading of post images/attachments (python)


Installing dependencies in ubuntu/debian
----------------------------------------

   ``sudo apt-get install python-yaml python-bs4 python-html2text``

Installing Python dependencies using python package installer (pip)
-------------------------------------------------------------------

From the checked out root for this project, type:

   ``sudo pip install --upgrade  -r pip_requirements.txt``

Note that PyYAML will require other packages to compile correctly under ubuntu/debian, these are installed by typing:

   ``sudo apt-get install libyaml-dev python-dev build-essential``


Configuration/Customization
===========================

See the `configuration file <https://github.com/wooni005/exitwp-for-hugo/blob/master/config.yaml>`_ for all configurable options.

Some things like custom handling of non standard post types is not fully configurable through the config file. You might have to modify the `source code <https://github.com/wooni005/exitwp-for-hugo/blob/master/exitwp.py>`_ to add custom parsing behaviour.

Known issues
============
 * Target file names are some times less than optimal.
 * Rewriting of image/attachment links if they are downloaded would be a good feature
 * There will probably be issues when migrating non utf-8 encoded wordpress dump files (if they exist).

Other Tools
===========
 * A Gist to convert WP-Footnotes style footnotes to PHP Markdown Extra style footnotes: https://gist.github.com/1246047
