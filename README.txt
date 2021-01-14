Simple Python Search Spider, Page Ranker, and Visualizer

This is a set of programs that emulate some of the functions of a
search engine.  They store their data in a SQLITE3 database named
'spider.sqlite'.  This file can be removed at any time to restart the
process.

You should install the SQLite browser to view and modify
the databases from:

http://sqlitebrowser.org/

This program crawls a web site and pulls a series of pages into the
database, recording the links between pages.

Note: Windows has difficulty in displaying UTF-8 characters
in the console so for each console window you open, you may need
to type the following command before running this code:

    chcp 65001

http://stackoverflow.com/questions/388490/unicode-characters-in-windows-command-line-how

Mac: rm spider.sqlite
Mac: python3 spider.py

Win: del spider.sqlite
Win: python spider.py

Enter web url or enter: https://en.wikipedia.org/wiki/Computer
[https://en.wikipedia.org/wiki/Computer]
How many pages:2
1 https://en.wikipedia.org/wiki/Computer (455539) 396
4 https://en.wikipedia.org/wiki/Computer_program (153267) 122
How many pages:

In this sample run, we told it to crawl a website and retrieve two
pages.  If you restart the program again and tell it to crawl more
pages, it will not re-crawl any pages already in the database.  Upon
restart it goes to a random non-crawled page and starts there.  So
each successive run of spider.py is additive.

Mac: python3 spider.py
Win: python spider.py

Enter web url or enter: https://en.wikipedia.org/wiki/Computer
[https://en.wikipedia.org/wiki/Computer]
How many pages:2
1 https://en.wikipedia.org/wiki/Computer (455539) 396
4 https://en.wikipedia.org/wiki/Computer_program (153267) 122
How many pages:

You can have multiple starting points in the same database -
within the program these are called "webs".   The spider
chooses randomly amongst all non-visited links across all
the webs.

If you want to dump the contents of the spider.sqlite file, you can
run spdump.py as follows:

Mac: python3 spdump.py
Win: python spdump.py

(45, None, 1.0, 1, 'https://en.wikipedia.org/wiki/Computer')
(35, None, 1.0, 5, 'https://en.wikipedia.org/wiki/Computer_hardware')
(30, None, 1.0, 6, 'https://en.wikipedia.org/wiki/Computer_network')
(26, None, 1.0, 22, 'https://en.wikipedia.org/wiki/Computer_graphics')
(26, None, 1.0, 16, 'https://en.wikipedia.org/wiki/Computer_data_storage')
(23, None, 1.0, 29, 'https://en.wikipedia.org/wiki/Computer_security')
(23, None, 1.0, 27, 'https://en.wikipedia.org/wiki/Computer_science')
(21, None, 1.0, 25, 'https://en.wikipedia.org/wiki/Computer_architecture')
(21, None, 1.0, 23, 'https://en.wikipedia.org/wiki/Computer_animation')
(20, None, 1.0, 9, 'https://en.wikipedia.org/wiki/Computer_memory')
(20, None, 1.0, 8, 'https://en.wikipedia.org/wiki/Computer-aided_design')
(19, None, 1.0, 32, 'https://en.wikipedia.org/wiki/Computer_mouse')
(19, None, 1.0, 17, 'https://en.wikipedia.org/wiki/Computer_keyboard')
(18, None, 1.0, 35, 'https://en.wikipedia.org/wiki/Computer_port_(hardware)')
(18, None, 1.0, 13, 'https://en.wikipedia.org/wiki/Computer_monitor')
(17, None, 1.0, 34, 'https://en.wikipedia.org/wiki/Computer_case')
(17, None, 1.0, 4, 'https://en.wikipedia.org/wiki/Computer_program')
(16, None, 1.0, 31, 'https://en.wikipedia.org/wiki/Computer_History_Museum')
(16, None, 1.0, 3, 'https://en.wikipedia.org/wiki/Computer_programming')
(15, None, 1.0, 33, 'https://en.wikipedia.org/wiki/Computer_speakers')
(14, None, 1.0, 51, 'https://en.wikipedia.org/wiki/Computer_worm')
(13, None, 1.0, 39, 'https://en.wikipedia.org/wiki/Computer_accessibility')
(12, None, 1.0, 52, 'https://en.wikipedia.org/wiki/Computer_security_compromised_by_hardware_failure')
(12, None, 1.0, 48, 'https://en.wikipedia.org/wiki/Computer_display')
(11, None, 1.0, 37, 'https://en.wikipedia.org/wiki/Computer-aided_engineering')
(11, None, 1.0, 26, 'https://en.wikipedia.org/wiki/Computer_engineering')
(11, None, 1.0, 21, 'https://en.wikipedia.org/wiki/Computer-aided_manufacturing')
(10, None, 1.0, 19, 'https://en.wikipedia.org/wiki/Computer_simulation')
(9, None, 1.0, 20, 'https://en.wikipedia.org/wiki/Computer_software')
(9, None, 1.0, 18, 'https://en.wikipedia.org/wiki/Computer_multitasking')
(8, None, 1.0, 79, 'https://en.wikipedia.org/wiki/Computer_fraud')
(8, None, 1.0, 14, 'https://en.wikipedia.org/wiki/Computer_speaker')
(7, None, 1.0, 80, 'https://en.wikipedia.org/wiki/Computer_crime')
(7, None, 1.0, 24, 'https://en.wikipedia.org/wiki/Computer_music')
(6, None, 1.0, 83, 'https://en.wikipedia.org/wiki/Computer_Fraud_and_Abuse_Act')
(6, None, 1.0, 45, 'https://en.wikipedia.org/wiki/Computer-generated_imagery')
(6, None, 1.0, 43, 'https://en.wikipedia.org/wiki/Computer_graphics_(computer_science)')
(6, None, 1.0, 7, 'https://en.wikipedia.org/wiki/Computer_cluster')
(5, None, 1.0, 82, 'https://en.wikipedia.org/wiki/Computer_security_software')
(5, None, 1.0, 77, 'https://en.wikipedia.org/wiki/Computer_Arts_Society')
(5, None, 1.0, 36, 'https://en.wikipedia.org/wiki/Computer_programmer')
(5, None, 1.0, 15, 'https://en.wikipedia.org/wiki/Computer_networking')
(5, None, 1.0, 12, 'https://en.wikipedia.org/wiki/Computer-on-module')
(4, None, 1.0, 96, 'https://en.wikipedia.org/wiki/Computer_games')
(4, None, 1.0, 84, 'https://en.wikipedia.org/wiki/Computer_and_network_surveillance')
(4, None, 1.0, 76, 'https://en.wikipedia.org/wiki/Computer_art_scene')
(4, None, 1.0, 69, 'https://en.wikipedia.org/wiki/Computer_Sciences_Corporation')
(4, None, 1.0, 63, 'https://en.wikipedia.org/wiki/Computer_processor')
(4, None, 1.0, 58, 'https://en.wikipedia.org/wiki/Computers')
(4, None, 1.0, 49, 'https://en.wikipedia.org/wiki/Computer_Graphics:_Principles_and_Practice')
102 rows.

This shows the number of incoming links, the old page rank, the new page
rank, the id of the page, and the url of the page.  The spdump.py program
only shows pages that have at least one incoming link to them.

Once you have a few pages in the database, you can run Page Rank on the
pages using the sprank.py program.  You simply tell it how many Page
Rank iterations to run.

Mac: python3 sprank.py
Win: python sprank.py

How many iterations:2
1 0.8661008669659187
2 0.33385777055186666
[(1, 6.206395645602267), (2, 0.3415420636736303), (3, 1.8868633242562223), (4, 1.859108333868576), (5, 4.4796663462149295)]

You can dump the database again to see that page rank has been updated:

Mac: python3 spdump.py
Win: python spdump.py

(45, 1.0, 6.206395645602267, 1, 'https://en.wikipedia.org/wiki/Computer')
(35, 1.0, 4.4796663462149295, 5, 'https://en.wikipedia.org/wiki/Computer_hardware')
(30, 1.0, 3.6639083631548535, 6, 'https://en.wikipedia.org/wiki/Computer_network')
(26, 1.0, 3.91952445191512, 22, 'https://en.wikipedia.org/wiki/Computer_graphics')
(26, 1.0, 3.147123780443594, 16, 'https://en.wikipedia.org/wiki/Computer_data_storage')
(23, 1.0, 2.4194581905620955, 29, 'https://en.wikipedia.org/wiki/Computer_security')
(23, 1.0, 2.5867171993844793, 27, 'https://en.wikipedia.org/wiki/Computer_science')
(21, 1.0, 2.002400240277605, 25, 'https://en.wikipedia.org/wiki/Computer_architecture')
(21, 1.0, 2.8517298492255603, 23, 'https://en.wikipedia.org/wiki/Computer_animation')
(20, 1.0, 2.2566690067832886, 9, 'https://en.wikipedia.org/wiki/Computer_memory')
(20, 1.0, 3.006695129950645, 8, 'https://en.wikipedia.org/wiki/Computer-aided_design')
(19, 1.0, 2.651225780594742, 32, 'https://en.wikipedia.org/wiki/Computer_mouse')
(19, 1.0, 2.1173326122162797, 17, 'https://en.wikipedia.org/wiki/Computer_keyboard')
(18, 1.0, 2.169338020440175, 35, 'https://en.wikipedia.org/wiki/Computer_port_(hardware)')
(18, 1.0, 2.437139679901021, 13, 'https://en.wikipedia.org/wiki/Computer_monitor')
(17, 1.0, 2.09242973784339, 34, 'https://en.wikipedia.org/wiki/Computer_case')
(17, 1.0, 1.859108333868576, 4, 'https://en.wikipedia.org/wiki/Computer_program')
(16, 1.0, 2.1531059841989872, 31, 'https://en.wikipedia.org/wiki/Computer_History_Museum')
(16, 1.0, 1.8868633242562223, 3, 'https://en.wikipedia.org/wiki/Computer_programming')
(15, 1.0, 1.9193017862495292, 33, 'https://en.wikipedia.org/wiki/Computer_speakers')
(14, 1.0, 2.120114279223275, 51, 'https://en.wikipedia.org/wiki/Computer_worm')
(13, 1.0, 1.6028647438872556, 39, 'https://en.wikipedia.org/wiki/Computer_accessibility')
(12, 1.0, 1.4202026832717638, 52, 'https://en.wikipedia.org/wiki/Computer_security_compromised_by_hardware_failure')
(12, 1.0, 1.432098731406353, 48, 'https://en.wikipedia.org/wiki/Computer_display')
(11, 1.0, 1.9207404842507403, 37, 'https://en.wikipedia.org/wiki/Computer-aided_engineering')
(11, 1.0, 1.5020638051985231, 26, 'https://en.wikipedia.org/wiki/Computer_engineering')
(11, 1.0, 1.5626735465698187, 21, 'https://en.wikipedia.org/wiki/Computer-aided_manufacturing')
(10, 1.0, 1.2475370374207044, 19, 'https://en.wikipedia.org/wiki/Computer_simulation')
(9, 1.0, 1.6651658482042775, 20, 'https://en.wikipedia.org/wiki/Computer_software')
(9, 1.0, 1.0462881969754358, 18, 'https://en.wikipedia.org/wiki/Computer_multitasking')
(8, 1.0, 1.6978583958093039, 79, 'https://en.wikipedia.org/wiki/Computer_fraud')
(8, 1.0, 0.983551708440628, 14, 'https://en.wikipedia.org/wiki/Computer_speaker')
(7, 1.0, 0.7432155386664471, 80, 'https://en.wikipedia.org/wiki/Computer_crime')
(7, 1.0, 0.6715888551174806, 24, 'https://en.wikipedia.org/wiki/Computer_music')
(6, 1.0, 2.215680524660844, 83, 'https://en.wikipedia.org/wiki/Computer_Fraud_and_Abuse_Act')
(6, 1.0, 0.82397276201033, 45, 'https://en.wikipedia.org/wiki/Computer-generated_imagery')
(6, 1.0, 1.147438087534479, 43, 'https://en.wikipedia.org/wiki/Computer_graphics_(computer_science)')
(6, 1.0, 0.5055695231422662, 7, 'https://en.wikipedia.org/wiki/Computer_cluster')
(5, 1.0, 0.7218429896468392, 82, 'https://en.wikipedia.org/wiki/Computer_security_software')
(5, 1.0, 0.4983688840955277, 77, 'https://en.wikipedia.org/wiki/Computer_Arts_Society')
(5, 1.0, 0.7220321120129571, 36, 'https://en.wikipedia.org/wiki/Computer_programmer')
(5, 1.0, 0.3741050888837143, 15, 'https://en.wikipedia.org/wiki/Computer_networking')
(5, 1.0, 0.5278165734775518, 12, 'https://en.wikipedia.org/wiki/Computer-on-module')
(4, 1.0, 0.4629906267319762, 96, 'https://en.wikipedia.org/wiki/Computer_games')
(4, 1.0, 0.6334026513903245, 84, 'https://en.wikipedia.org/wiki/Computer_and_network_surveillance')
(4, 1.0, 0.3885241128536977, 76, 'https://en.wikipedia.org/wiki/Computer_art_scene')
(4, 1.0, 0.6109857035505825, 69, 'https://en.wikipedia.org/wiki/Computer_Sciences_Corporation')
(4, 1.0, 0.24848140385090464, 63, 'https://en.wikipedia.org/wiki/Computer_processor')
(4, 1.0, 0.3387387946860266, 58, 'https://en.wikipedia.org/wiki/Computers')
(4, 1.0, 0.5902188058824244, 49, 'https://en.wikipedia.org/wiki/Computer_Graphics:_Principles_and_Practice')
102 rows.

You can run sprank.py as many times as you like and it will simply refine
the page rank the more times you run it.  You can even run sprank.py a few times
and then go spider a few more pages sith spider.py and then run sprank.py
to converge the page ranks.

If you want to restart the Page Rank calculations without re-spidering the
web pages, you can use spreset.py

Mac: python3 spreset.py
Win: python spreset.py

All pages set to a rank of 1.0

Mac: python3 sprank.py
Win: python sprank.py

How many iterations:50
1 0.1363580068344346
2 0.0741059689889334
3 0.04591500176294517
4 0.030980458227999958
5 0.02239285115242037
6 0.016122825714503512
7 0.011772598106073475
...
42 5.866350392014355e-06
43 4.932019152047571e-06
44 4.147168078427634e-06
45 3.487473426329188e-06
46 2.9327706670725222e-06
47 2.4664270876524046e-06
48 2.074266178501819e-06
49 1.7445242090615175e-06
50 1.467216064808568e-06
[(1, 6.729635889886331), (2, 0.24805834945205052), (3, 1.8320792652953868), (4, 1.2682764637610484), (5, 5.869957717981504)]

For each iteration of the page rank algorithm it prints the average
change per page of the page rank.   The network initially is quite
unbalanced and so the individual page ranks are changing wildly.
But in a few short iterations, the page rank converges.  You
should run prank.py long enough that the page ranks converge.
