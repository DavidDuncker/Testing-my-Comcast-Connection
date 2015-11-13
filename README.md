# Testing-my-Comcast-Connection

This mini-project is designed to help me diagnose why my internet connection intermittently slows down. It includes a bash script repeatedly pings my personal router, google.com, facebook.com, and other popular websites using IP packets of various sizes, and stores the results in a MySQL database.

If run correctly, the resultant MySQL table should look something like this:
_______________________________________________________________________________________________

mysql> select * from ping;
+---------------------+----------------+---------+-----------+-----------+-----------+-------+

| time                | host           | bitsize | minrtt    | avgrtt    | maxrtt    | ploss |

+---------------------+----------------+---------+-----------+-----------+-----------+-------+

| 2015-11-12 22:22:06 | 10.0.0.1       |      60 |      1.35 |      2.73 |     12.81 |     0 |

| 2015-11-12 22:23:24 | google.com     |      60 |     18.21 |     22.70 |     35.36 |     0 |

| 2015-11-12 22:24:42 | youtube.com    |      60 |     18.22 |     21.20 |     38.27 |     0 |

| 2015-11-12 22:26:00 | facebook.com   |      60 |     73.85 |     79.65 |    130.33 |     0 |

| 2015-11-12 22:27:19 | github.com     |      60 |     23.58 |     27.62 |     43.88 |     0 |

| 2015-11-12 22:28:37 | bing.com       |      60 |     18.22 |     28.32 |    104.21 |     0 |

| 2015-11-12 22:30:05 | instagram.com  |      60 | 999999.99 | 999999.99 | 999999.99 |   100 |

| 2015-11-12 22:30:12 | 10.0.0.1       |      60 |      1.44 |      1.92 |      6.07 |     0 |
| 2015-11-12 22:31:30 | yahoo.com      |      60 |     37.24 |     41.63 |     55.88 |     0 |
| 2015-11-12 22:32:51 | espn.com       |      60 |     71.31 |     72.96 |     79.28 |     0 |
| 2015-11-12 22:34:19 | www.amazon.com |      60 | 999999.99 | 999999.99 | 999999.99 |   100 |
| 2015-11-12 22:35:37 | wikipedia.com  |      60 |     32.11 |     36.25 |     66.88 |     0 |
| 2015-11-12 22:36:55 | twitter.com    |      60 |     85.40 |     89.61 |    104.36 |     0 |
| 2015-11-12 22:38:24 | ebay.com       |      60 | 999999.99 | 999999.99 | 999999.99 |   100 |
| 2015-11-12 22:39:42 | blogspot.com   |      60 |     18.45 |     21.94 |     36.60 |     0 |
| 2015-11-12 22:39:49 | 10.0.0.1       |      90 |      1.43 |      2.41 |      7.97 |     0 |
| 2015-11-12 22:41:07 | google.com     |      90 |     19.06 |     22.71 |     37.94 |     0 |
| 2015-11-12 22:42:25 | youtube.com    |      90 |     19.34 |     22.84 |     27.69 |     0 |
| 2015-11-12 22:43:43 | facebook.com   |      90 |     74.54 |     81.07 |    138.18 |     0 |
| 2015-11-12 22:45:01 | github.com     |      90 |     22.05 |     25.95 |     40.67 |     0 |
| 2015-11-12 22:46:20 | bing.com       |      90 |     19.24 |     22.07 |     28.08 |     0 |
+---------------------+----------------+---------+-----------+-----------+-----------+-------+
21 rows in set (0.00 sec)
______________________________________________________________________________________________________

where "Host" is the server being pinged, "bitsize" refers to the packet size, "minrtt", "avgrtt", and "maxrtt" refers to the minimum, average, and maximum amount of time for my internet connection to respond to each of the several pings sent to the server.

This repo does not include the MySQL database itself. 
