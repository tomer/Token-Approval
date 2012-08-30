The purpose of this project is to allow an easy way to block access to certain pages and applications running on servers in order to prevent malicious usage by bots, spammers and spiders. In order to be system independent so it won't matter which applications are used on the server and won't require using their API at all, if exists. Instead, we use Apache's mod_rewrite to redirect users to our challenge page, which does one simple task – set a cookie on the user browser and reload the page. Than, Apache mod_rewrite will load the usual page instead of our challenge page, and the user won't get any further redirections to the script for a given time. 

The challenge page is simply setting a cookie using JavaScript. I find it enough to block all the spam bots from posting nuts on my sites, but this might change in the future. At the moment it will happen, the site administrator will have to tweak the blocking page until it is complicated enough to block the upgraded bots.

Here is [a blog post I wrote][1] few years ago. Funny enough but the same blocking method still going strong five years after! 

The repository contains an .htaccess file with few examples to block spam bots. Place the script on /token/ or any other directory as you prefer and set the rewrite rules to redirect to the script. It is recommended to keep the rules that are unique to each application in its own directory in order to keep site performances at its best. Also, it is recommended to change the cookie value as well as its name to something unique to your site, so spammers won't be able to use common values. It needs to be changed on the HTML page itself as well as every .htaccess file that redirects to the script.

Please let me know if you have suggestions for this script as well as bug reports.

— Tomer Cohen, http://tomercohen.com



[1]: http://tomercohen.com/cookies-spam-protection
