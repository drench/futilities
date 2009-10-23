futilities
==========

* ## acuff

	Attemps to generate a list of all configuration files the local
	Apache installation uses. Great when you're working on a new and/or
	strange Apache installation. Requires Perl 5 with no extras,
	and shell access to a server 

	For more information: http://dren.ch/apache-config-finder/

* ## cpansion

	If you, like me, find yourself on the edge of your seat awaiting
	the next update of DateTime::Format::RFC3339, cpansion is for you.

	It takes one argument: the name of a Perl module.
	Then it scrapes the module's page on search.cpan.org to find its current
	version number and prints it to standard output for you to examine.

	Requires Perl 5 with LWP and HTML::TokeParser.

* ## modiff

	Your version control system is happy to tell you how your working
	version differs from the last committed version, but it won't
	tell you how it differs from what's actually installed.

	Modiff is for those times you suspect whoever installed the version
	of some Perl module you're working on now never bothered to check it in,
	and a "make install" can mean wiping the only known working copy.

	Requires Perl 5 and skepticism.

	For a less coherent explanation: http://dren.ch/perl-module-diff/

* ## weedagents

	If you use ssh-agent, you probably have a bunch of dead agents in your
	/tmp directory. Weedagents runs through them and weeds the dead ones.

	Requires Ruby 1.something (1.8 will do) and a system that doesn't clean
	/tmp enough to your liking.
