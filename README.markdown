futilities
==========

* ## acuff

    Attemps to generate a list of all configuration files the local
    Apache installation uses. Great when you're working on a new and/or
    strange Apache installation. Requires Perl 5 with no extras, and
    an urgent need to know the location of a mysterious RedirectMatch.

* ## alac2mp3

    When I buy music from Bandcamp, I choose Apple Lossless, since, unlike FLAC,
    iTunes can play the format. Since I have devices that won't play ALAC, I
    want mp3 format as well. I can make iTunes do the conversion, but it's
    no fun at all, so I wrote alac2mp3. I haven't tried, but this thing may
    also convert AAC (iTunes store) format files to mp3 as well.

    Requires `afconvert` (standard on OS X), `lame`, Ruby with the taglib gem,
    and ALACs.

* ## cpansion

    If you, like me, find yourself on the edge of your seat awaiting
    the next update of DateTime::Format::RFC3339, cpansion is for you.

    It takes one argument: the name of a Perl module.
    Then it scrapes the module's page on search.cpan.org to find its current
    version number and prints it to standard output for you to examine.

    Requires Perl 5 with LWP and HTML::TokeParser.

* ## doublebounce_faster

    Long-time qmail administrators (and that's most of them I think)
    configured their servers to blackhole double bounce messages years ago.

    Meanwhile, qmail keeps these messages you will ignore in its queue in
    its doomed attempt to deliver bounces to ocaubag255@brasiltelecom.net.br
    and the like for 7 days.

    Running doublebounce_faster (as root) searches your queue for all the
    messages over a day old destined to double bounce and makes qmail
    think it's been trying to deliver them since the Ford administration.

    Once qmail notices these (`svc -a /service/qmail` to make that time NOW),
    it gives them one more chance at delivery before discarding them forever.

    Requires Ruby 1.something and a qmail installation with a queue
    overflowing with crap.

* ## flac2mp3

    I sometimes want to convert a directory of flacs into mp3s.
    Maybe you do too.

    Flac2mp3 expects to find `flac` and `lame` executables in your `$PATH`.
    It also expects your flac files to begin with numbers, and uses
    them to set id3 track numbers in the mp3 files.

    The call to `lame` uses parameters that I've read are decent
    and they sound all right to me: `-V2 --vbr-new -q0 --lowpass 19.7`.

    Also any arguments you specify on the `flac2mp3` command line are passed
    straight to `lame`, so you might find yourself wanting to tack on
    `--ta` (artist), `--tl` (album), `--ty` (year) and/or `--tg` (genre).

    When `flac2mp3` finishes, you're left with not just mp3s, but also
    uncompressed wavs and of course the original flacs.
    I thought about having it remove the wav files automatically,
    but sometimes I want them, like when I want burn a CD.
    Run `rm *.wav` if it really bothers you.

    Requires ruby, flac, lame, and above-board flac files.

* ## modiff

    Your version control system is happy to tell you how your working
    version differs from the last committed version, but it won't
    tell you how it differs from what's actually installed.

    Modiff is for those times you suspect whoever installed the version
    of some Perl module you're working on now never bothered to check it in,
    and a `make install` can mean wiping the only known working copy.

    Requires Perl 5 and skepticism.

* ## phpmyadmin-backup

    MySQL and PHP can be bad enough all by themselves.

    But add a web host that won't allow shell access (lame) or
    direct connections to port 3306 (understandable, but inconvenient),
    and there's no nice way to do automated backups.

    I found a Python script to pull backups through phpMyAdmin, but it has
    some problems. The big one is that Python's urllib2 honors `robots.txt`,
    and the server I needed to back up had "Disallow: /" in it.
    10 minutes of googling later, I still did not know to override this
    so I decided to write my own version, not in Python.

    I thought about writing it in Ruby, but `gem install mechanize`
    did not go well (some complications with `libxslt`) so Perl it is!

    Requires Perl 5, WWW::Mechanize, and restricted access to "your" server.

* ## ssldates

    How do you know when an SSL certificate is due to expire?

    Do you point your browser at the site, click the little "lock" icon,
    and examine the certificate info? Or do you just wait until people
    start complaining that your site is giving them a scary security
    warning the morning after?

    No, silly, you use `ssldates`!

    I know what you're going to ask: "Hey, what about SSL services that
    are not HTTP? Can you check those, too smart guy? These are CRITICAL
    for my ENTERPRISE! FIVE NINES!"

    I have SSL certificates on non-HTTP services such as POP3, IMAP4, and
    SMTP and I can assure you ssldates works on these too.

    Requires Perl 5 with the Net::SSLeay module and a proactive attitude,
    I guess.

* ## timemachiner

    Let's say you have a TODO list in a text file that you update a lot.
    If you're running OS X's Time Machine, it has all your old versions,
    but do you really want to use that crazy Star Wars interface to look
    at them? Wouldn't you rather use `git` (and friends like `tig`)?

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

* ## twid

  If you use the Twitter API, you often need a user's ID number, as opposed to
  the screen name. You could use the API to look this up, but why bother when
  you can get this ID by parsing the public HTML? This works for private
  accounts, too! It doesn't work for suspended accounts. Sorry!

  Example usage:

  ```bash
  twid kree10
  ```

  Requires `curl` and [https://github.com/ericchiang/pup](`pup`).

* ## weedagents

    If you use `ssh-agent`, you probably have a bunch of dead agents in your
    `/tmp` directory. Weedagents runs through them and weeds the dead ones.

    Requires Ruby 1.something (1.8 will do) and a system that doesn't clean
    `/tmp` enough to your liking.

* ## wpdb

    If you work on several different WordPress sites, you may want `wpdb`.
    Even if you only work on a single WordPress site, you may want `wpdb`.

    `wpdb` is a wrapper around `mysql` that looks in (and around!) your working
    directory for a `wp-config.php` file. If it finds one, it grabs the host
    name, database name, username and password for it and executes `mysql`,
    saving you time and/or money (or maybe just time, if you're doing it
    fixed-rate or worse, gratis).

    Example:

        % cd /path/to/some/wordpress/site
        % echo "show tables;" | wpdb

    Look, you don't even have to be in the root directory:

        % cd /path/to/some/wordpress/site/wp-admin/css
        % echo "select count(*) from wp_users" | wpdb

    But that's not all! It will run mysqldump instead if you ask it to:

        % cd /path/to/some/wordpress/site/wp-includes/js/tinymce
        % wpdb --exec=mysqldump > /tmp/wp-snapshot.sql

    You can also explicitly point at a Wordpress install in another directory:

        % wpdb --wp_conf=/path/to/another/wordpress/site

    wpdb will pass on any extra arguments you specify to mysql too:

        % wpdb --i-am-a-dummy

    I wrote this in Perl because I lifted the bulk of it from
    phpmyadmin-backup (see above).

    Requires Perl 5, little patience, and little else.
