---
layout: post
title: Blog Migration
date: '2025-10-04 20:45:00 +000'
categories:
  - Technology
tags:
  - blog
  - migration
  - wordpress
  - jekyll
comments: []
---

<div style="text-align: center;">
  <img src="/assets/images/2025-10-04-blog-migration.png" alt="Blog Migration Image" style="max-width: 300px; width: 100%; height: auto; display: block; margin: 0 auto;" />
  <div style="font-size: 0.9em; color: #555; margin-top: 8px;">
    <em>Image by ChatGPT</a></em>
  </div>
</div>

My goal with this blog was not just to write, but also to explore the technologies behind blogging platforms.  
After experimenting with WordPress for a while and hosting it on a VM in DigitalOcean, I decided to move to a managed solution.  
Hostinger provides both a domain and managed WordPress at a very low price—around ~₹200 for the first year. Unfortunately, from the second year onward, the renewal fee for the domain jumps to about ~₹2500, which is quite steep for a blog like this where posts are rare and readership is minimal, if any. That’s when I decided to migrate to GitHub Pages, powered by Jekyll.

Last year, I went ahead and renewed by paying ~₹2500. But when the renewal came up again this year, I didn’t want to continue. Even though the reminder came a month before expiration, I ignored it and only realized later that the domain was down. While exploring Hostinger’s console, I found access to phpMyAdmin, which allowed me to extract the articles.

## Migration

For the migration, there are three possible approaches:

1. If the site is still up, use a migrator tool and point it to the blog—it will handle everything.  
2. If the MySQL database powering WordPress is accessible, point the [jekyll-import](https://import.jekyllrb.com/docs/wordpress/) tool to it.  
3. Rewrite everything manually (possible since the raw content is available in phpMyAdmin).

Option (1) wasn’t feasible, since the domain had expired and renewing it was out of the question.  
Option (2) wasn’t directly possible either, as Hostinger does not expose MySQL connections for security reasons.  
Option (3) was unattractive—I wasn’t going to rewrite everything manually. Being a software engineer, I knew I could automate this somehow.

Lightbulb moment: I could export the database to a SQL file, import it into a local MySQL instance, and then proceed with Option (2).

## Steps

Here’s how it went:

* Export the database using phpMyAdmin (one click, worked flawlessly).  
* Start a local MySQL instance:  
   ```bash
   docker run --name jekyll-db \
   -e MYSQL_ROOT_PASSWORD=my-secret-pw \
   -e MYSQL_DATABASE=wp_local \
   -e MYSQL_USER=jekyll_user \
   -e MYSQL_PASSWORD=jekyll_pw \
   -p 3306:3306 \
   -d mysql:8.0
   ```
* Import the exported SQL file:  
   ```bash
   docker exec -i jekyll-db mysql \
   --host=127.0.0.1 \
   -u jekyll_user \
   -pjekyll_pw wp_local \
   < u364928731_ZpTTJ.sql
   ```
* Create a blank directory `blog` and run `jekyll-import`:  
   ```bash
   jekyll-import wordpress \
   -dbname wp_local \
   --user jekyll_user \
   --password jekyll_pw \
   --host 127.0.0.1 \
   --port 3306 \
   --table_prefix wp_ \
   --comments \
   --categories \
   --tags \
   --more_excerpt \
   --more_anchor
   ```
* In a blink, the `_posts` directory was generated with all my posts.  
* Cleanup:  
   ```bash
   docker stop jekyll-db
   docker rm jekyll-db
   ```

Finally, I set up the [GitHub Pages repository](https://github.com/gbhat618/gbhat618.github.io) and copied the `_posts` into it, fixed up a few things.

---

I still wanted a domain, so I plan to get one from [Epik.com](https://www.epik.com/). They allow purchasing a domain for 10 years.  
Even if I’m not interested in keeping it beyond that, 10 years feels long enough to not worry about renewal fees for now.