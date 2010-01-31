futilities
==========

* ## acuff

	Attemps to generate a list of all configuration files the local
	Apache installation uses. Great when you're working on a new and/or
	strange Apache installation. Requires Perl 5 with no extras, and
	an urgent need to know the location of a mysterious RedirectMatch.

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

* ## timemachiner

    Let's say you have a TODO list in a text file that you update a lot.
    If you're running OS X's Time Machine, it has all your old versions,
    but do you really want to use that crazy Star Wars interface to look
    at them? Wouldn't you rather use git (and friends like tig)?

    Timemachiner figures out where your Time Machine backups are,
    finds all the previous revisions of your file (the 1st argument), and
    commits them to a git repository (the 2nd argument), creating the
    repo if necessary (you probably don't want to use this on an existing
    repo anyway). Timemachiner also forges the commit timestamps to match
    Time Machine's backup times.

    Example usage:

    % timemachiner /Users/drench/TODO /Users/drench/gitified-TODO

    Timemachiner has its own large, unwritten TODO list of its own.

    Requires OS X, Ruby 1.whatever-ships-with-OS X, Time Machine, and git.

* ## weedagents

	If you use ssh-agent, you probably have a bunch of dead agents in your
	/tmp directory. Weedagents runs through them and weeds the dead ones.

	Requires Ruby 1.something (1.8 will do) and a system that doesn't clean
	/tmp enough to your liking.
