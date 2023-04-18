13 April 2023: wsChoicer ver 1.85: a php/javascript app for helping small groups chose alternatives

What is wsChoicer?

  wsChoicer is designed to help small groups collaboratively choose from a mid-size set of suggestions.
  Each "user" (or member) of the group can add/rate/rank/recommend suggestions -- using their own stated preferences
  and those of other members.

How does it work?

   Using a several step process, that may take several days (or weeks) to unfold!

  1) Adding suggestions
     During this phase, members can add a suggestion. Several variables (as specified by the admin) can
     be entered for each suggestion. For example, a "publication year", a "cost", a "short description", etc.
  2) Rates, categories, notes
     During (or after) the adding suggestions phase members can rate the current suggestions.
     A 1 to 4 scale is used, with 4 being better than 1.
     Each member can also assign a category to each suggestion -- and share this categorization with other members.
     And -- members  can provide links to information, or enter longer descriptive notes.
  3) Ranking
     After suggestions have been collected, each member can rank the suggestions.
     wsChoicer uses a simple ranking system: suggestions can be assigned to a "Top 9" or a "Next best 9".
     All other suggestions are worse than next best 9!
     This ranking may be based on personal rating, or on average (across all members) rating. But it does not have to be.

  4) Recommendation
  	Once enough  members have ranked the suggestions, each member can you choose which ones to recommend.
  	Recommendations can be based on ratings, recommendations, notes, and categories. But they do not have to be.

  5) A member can use their (or another member's) recommendations to create a schedule
     Several types of schedules are supported: a hourly schedule, a calendar schedule, a quantity schecule,
     or an 'ordered by type' schedule.
     The order (such as the time in day) of a schedule can be readily changed and tweaked.

  Why these several steps? ... to use triaging to reduce how many suggestions one needs to consider!

wsChoicer has a lot of options to help members puruse, compare, and otherwise think about the suggestions.
  For further details: see choicer_help.html

   -----------------------------------------------------

Installation Notes

  wsChoicer is distributed in a .zip file, with a name like wsChoicer_1_85.zip.

    This zip file should be unzipped into an empty directory; and this empty directory should be
    web accessible; by an http server supporting php (ver 7.0 or above).

  After wsChoicer is unzipped, you should open it in your favorite browser.
    For example  -- assume your web server handles http://www.mysite.org/, and
    wsChoicer was installed in D:\www\wsChoicer (with D:\www the root directory for requests):
        http://www.mysite.org/wsChoicer/index.php

  First open:
    A configuration screen is shown, wherein you are asked to specify a few administrative variables.
    In particular, 
       * the administrator password.
       * a short introduction displayed on the home page.
   There is also a link to this document (readMe.txt).

  You should then reopen wsChoicer.

  Second open:
    You should specify a project -- click on the gear key (upper right corner) to logon as admin

      Use the password you specified above.

    In either case, wsChoicer will prompt you to copy several parameter files

  You should then reopen wsChoicer again.


  Third open:
    Logon to the project you created, as `admin` -- use the admin password you saved in the first step!
    And then use the "edit parameter" button to customize the project.

  Your installation of wsChoicer is now ready for public use!

  Notes:

     * You can change the administrative password by editing params/choicer_init.php.
       That is: it can NOT be modified using wsChoicer's on line tools

     * The short home-page-intro can be modified by editing data/projectIntro.html.
       Note that this intro is NOT specific to a project.

     * You can  modify the parameters of an existing project -- such as the intro and list of members,
       by logging on as admin. Once you logon as admin you can select a button. For parameter modification,
       the Set Parameters button.

     * To create a new project: click the gear icon at the top left corner of the home page.

     * index.php is the home page for wsChoicer. It contains a few parameters that an ambitious admin
       can modify.

  Security notes:
     wsChoicer is NOT very secure. But it does have a few security features:
       * A single administrative password (for all projects). That is stored as a MD5 hash (the actual
         password is NOT stored).
       * Optional project specific passwords -- same password for everyone who tries to access a project.
       * Optional project specific list of valid member names -- no one else will be granted entry.
       * A downloadKey (stored as an MD5 hash), and a list of members, can be used to limited who can
         use wsChoicer to download content from a private server.

     Note that wsChoicer makes no attempt to encrypt communications  -- so it is NOT explicitly secure
     against man-in-the-middle attacks  (although using https:// should help with that).

The following directories are created.

  None of them contain files that a typical administrator will work with on a frequent basis.
  However, a few of them can be manipulated with admin tools -- such as "cleaning up old and unused files"
  or "archiving current suggestions".

  css     : css files
  data    : the `project` files -- each project has its own subdirectory under data/, with its own set of subdirectorie.s
  lib     : js and php libraries
  imgs    : various .gif and .png images used by wsChoicer
  include : code and documentation files used by wsChoicer
  other   : some useful other files. In particular: choicer_get.php
  params  : contains the choicer_init.php file (that contains the admin password's MD5) -- the admin
            can modify this.
            And several template files used  when a new project is created.


A note on implementation:
   wsChoicer uses small data files to store information.
   mySql (or some other database) engine might be more efficient, but as of now -- for reasons of portablity
   and ease of setup -- a file based system is used.

   For more details: see data/readMe.txt

  -------------------

Contact: Daniel Hellerstein. danielh@crosslink.net.
       http://www.wsurvey.org/distrib, or  https://github.com/dHellerstein

Disclaimer:

    wsChoicer is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    wsChoicer is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    If you did not receive a copy of the GNU General Public License,
    see <http://www.gnu.org/licenses/>.

    Note: wsChoicer uses security measures that are not strong.
          In particular: if you do not control access to the directory that wsChoicer 
                         (its index.php and other files) is installed on  ...
                     --  you should NOT install wsChoicer on your web server!


