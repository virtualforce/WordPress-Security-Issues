# Wordpress Security Issues – One of the hottest topics
How to protect your wordpress website from getting hacked is one of the hottest topics now days. Regardless of the fact that wordpress has increased its security by many folds, the websites built in wordpress are still easily hack-able as compared to the websites built on other networks. 
Today we would discuss how we can secure our Wordpress website by implementing few simple security checks (apart from strong passwords etc that we already know).

## 1-	Change wp database prefix
Database is like brain for the website as it contains every single piece of information being populated in the website AND at the same time it is all that a hacker would want to access to hack a website  

Wordpress has a default database prefix structure of wp_ . A smart person would always change the default prefix of wordpress database. This can be done while installation of wordpress website. Change the database prefix to something like “wo10Ki” etc. This would make it much harder for the hacker to run the default scripts and hack the website.

But wait. Most of the people actually think of implementing the security after complete website is built. To implement the same process in already built website. Here is what you would do.
1.	Go to the database manually and change all the table names prefix by your desired prefix. In our case we would keep it like“wo10Ki”. So for example the first table would be “wp_commentmeta” and we would change it as “wo10Ki_commentdata”. Change all the tables using the same technique.
2.	Now go to your WP Config File (Located in the main folder of wordpress) and write this simple line:
~~~
$table_prefix  = 'wo10Ki_';
~~~
This would change tell your website to use the new prefix from the database.

## 2. Change default User: 
The second most foolish and most common mistake that web make is that we keep the default user as ADMIN. This gives a user first free pass to heaven (DATABASE). Always keep the user name for your website unique (along with password ofcource). In an already built website. This can be done through Users menu from wordpress backend.

## 3. Disable theme and File Editor:
By default users are allowed to edit and save the theme files through the wordpress backend. This is used by most hackers as a way to hack websites. It is better to disable that option.
We can disable this options from Wpconfig.php file by adding 
~~~
define( 'DISALLOW_FILE_EDIT', true );
~~~

## 4. Other things to do 
Apart from these main 3 points. Here is a long list of checks that we can apply to secure the website.
1-	Enable 404 detection (All non-normal links or direct file link to be re-directed to 404).
2-	Brute force protection. Website would lock and block after 3 non successful attempts
3-	File change detection. The website would block any direct file change request and would maintain the record of it
4-	Hide login area. Login url changed.
5-	Force SSL on all pages
6-	Only allow strong pass when creating new url’s
7-	Protect System Files
8-	Disable Directory Browsing
9-	 Filter Request Methods
10-	 Filter Suspicious Query Strings in the URL
11-	Filter Non-English Character
12-	Filter Long URL Strings
13-	Remove File Writing Permissions
14-	 Disable PHP in Uploads
15-	 Disable login error messages
16-	Changed the default user of wordpress
17-	Changed wp database prefix

All of these mentioned checks can be managed by a great plugin (IThemes Security: https://wordpress.org/plugins/better-wp-security)
