## sysstat - System performance tools for the Linux operating system...

(C) 1999-2016 Sebastien GODARD (sysstat <at> orange.fr)

The latest version of sysstat can always be found on my web site at:

[http://pagesperso-orange.fr/sebastien.godard/](http://pagesperso-orange.fr/sebastien.godard/)

See the CHANGES file to know the new features/improvements/bug fixes added
in this release of sysstat.

You can also track sysstat development on [GitHub](https://github.com/sysstat/sysstat)
and clone its public repository with:

    git clone git://github.com/sysstat/sysstat


### Installation


The sysstat utilities are a collection of **performance monitoring tools** for
Linux. These include _mpstat, iostat, tapestat, cifsiostat, pidstat,
sar, sadc, sadf_ and _sa_ tools.

The first stage is to configure sysstat for your system:

	./configure

You can set several variables and parameters on the command line.
Please enter `./configure --help` to display them.
There is another way to configure sysstat instead of entering `./configure`:
this is the **Interactive Configuration script** (_iconfig_) which will ask you
for the value of the main sysstat variables and parameters.
Enter `./iconfig` then answer the questions or enter Return to accept
the (sane) default values. For yes/no questions, please answer 'y' or 'n'
(without the quotes): It is case sensitive! You can also enter '?' to get
a help message that will explain the meaning of each variable or parameter.

The next stage is to build the various binary files. Enter:

	make

Then log in as root and enter:

	make install

(see next section to know the files that are installed).
That's all!

Of course tell me if there are any problems. This is the only way I can improve
'sysstat'. Please also remember to read the FAQ included in this package.

Patches and suggestions for improvements are always welcome!
Send them to "sysstat (at) orange (dot) fr".

#### Support sysstat!

If you are reading this README file then you are probably about to use the sysstat tools
to help you monitor your system and maybe troubleshoot some performance issues. Good choice.
Sysstat is made for you. Moreover sysstat is free software and always will be.

Yet have you ever considered making a donation to sysstat, regardless of how much your
contribution is? This in turn would encourage me to keep up the work as good as it can be...
Oh, and it would certainly also help me explain to my wife why I spend so much time in front
of my computer instead of taking care of the household ;-)

Go to my web page and [click on the Donate button](http://pagesperso-orange.fr/sebastien.godard/) on the left!


### Files that are installed

Here is the list of files installed by sysstat, when you ask for a
complete installation.
${PREFIX} is the value of the PREFIX variable defined in the Makefile
(usually set to `/usr/local` or `/usr`).

    ${PREFIX}/lib/sa/sadc
    ${PREFIX}/lib/sa/sa1
    ${PREFIX}/lib/sa/sa2
    ${PREFIX}/bin/sar
    ${PREFIX}/bin/sadf
    ${PREFIX}/bin/iostat
    ${PREFIX}/bin/tapestat
    ${PREFIX}/bin/mpstat
    ${PREFIX}/bin/pidstat
    ${PREFIX}/bin/cifsiostat
    ${PREFIX}(/share)/man/man8/sadc.8
    ${PREFIX}(/share)/man/man8/sa1.8
    ${PREFIX}(/share)/man/man8/sa2.8
    ${PREFIX}(/share)/man/man1/sar.1
    ${PREFIX}(/share)/man/man1/sadf.1
    ${PREFIX}(/share)/man/man1/iostat.1
    ${PREFIX}(/share)/man/man1/tapestat.1
    ${PREFIX}(/share)/man/man1/mpstat.1
    ${PREFIX}(/share)/man/man1/pidstat.1
    ${PREFIX}(/share)/man/man1/cifsiostat.1
    ${PREFIX}/share/locale/*/LC_MESSAGES/sysstat.mo
    ${PREFIX}/share/doc/sysstat-x.y.z/*
    /var/log/sa
    ${INIT_DIR}/sysstat
    /lib/systemd/system/sysstat.service			if OS uses systemd
    /lib/systemd/system/sysstat-collect.service	if OS uses systemd
    /lib/systemd/system/sysstat-collect.timer	if OS uses systemd
    /lib/systemd/system/sysstat-summary.service	if OS uses systemd
    /lib/systemd/system/sysstat-summary.timer	if OS uses systemd
    /etc/sysconfig/sysstat
    /etc/sysconfig/sysstat.ioconf
    /etc/cron.d/sysstat
    /etc/rc.d/rc.sysstat			(depending on your distro)
    ${RC_DIR}/rc2.d/S03sysstat
    ${RC_DIR}/rc3.d/S03sysstat
    ${RC_DIR}/rc5.d/S03sysstat

sysstat may also install some links in `${RC_DIR}/rc[0146].d/` directory
if _chkconfig_ is used.

### Miscellaneous

The sysstat commands are only front-ends to the kernel proc filesystem...
They cannot display statistics that Linux does not
provide, nor can they be more accurate than Linux is.
The sysstat package no longer supports 2.4.x and older kernels.
Note that all kernels do not necessarily have all the statistics that
sysstat commands can display, depending on their version or their
configuration options.

It has been designed with National Language Support (NLS) in mind, using
the GNU gettext package (available at [http://www.gnu.org](http://www.gnu.org)).
sysstat has been translated into several languages.
Anyway you are welcome if you want to make other translations available ;-)
Please read the README-nls file in the nls directory before.

--

Sebastien GODARD - sysstat (at) orange (dot) fr

