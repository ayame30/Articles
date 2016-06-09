This page is about how to conduct SEO to a website in terms of technical, design and content aspect.

SEO is a process to improve the searchability of a website in Google, Yahoo or other search engine. Since Google has the largest market share of search engine, traditionally it is the only one being considered. Despite of that, most of the tasks will improve the result in other search engines. The way of doing SEO can be spending a lot of budget and having a chance of being punished by the search engine, This page will focus on how to be easier to be searched in Google in a low-cost, safe way. The algorithm created by Google is having frequent update every month due to improvement, bug-fix, new technology, social env change and some more cause. The following instruction is aimed to give a guild to those "unchanged" concepts, however, you should also read updated news about SEO. Some online resources:

1. http://searchengineland.com/
2. https://moz.com/learn/seo
3. http://seositecheckup.com/
4. http://nibbler.silktide.com/en_US


## Early works
Before doing everything, you should first record down the current performance in search engine. So that you can compare the result after you have conduct the tasks.
A few metrics you should record:

1. [Google PageRank](https://en.wikipedia.org/wiki/PageRank)
2. [Moz Domain Authority](https://moz.com/learn/seo/domain-authority)
3. [Moz Page Authority](https://moz.com/learn/seo/page-authority)
4. Alexa Ranking in global
5. Alexa Ranking in targeted country
6. [External Backlinks](https://moz.com/learn/seo/external-link)
7. Referring Domains

There is a [tool](http://checkpagerank.net/) to get most of the metrics above.
For Alexa Ranking, you may need to go to [Alexa](http://www.alexa.com/)

After these, you should draft a list of targeted keywords which you want your visitors to see your website in Google when they enter the keywords.
For example, [keystoneprep.com](keystoneprep.com) this is a project we have helped the SEO

The keywords we should are:
keystone prep, keystone English, keystone academic, keystone education, keystone summer, keystone SAT, keystone ACT, keystone SSAT, Keystone HK Summer, Keystone Seoul Summer, Keystone hk, keystone hong kong, keystone seoul, keystone Korea, SSAT summer, SSAT hk summer, SSAT hong kong summer, SSAT seoul summer, keyword: ACT hk summer, ACT seoul summer, SAT hk summer, SAT hong kong summer, SAT seoul summer


## Technical tasks
In terms of technical, the aim is to improve the accessibility to visitors and the how easy to be understand by machine.

###Accessibility
It means can anyone including mobile user can visit the website in a reasonable time with reasonable UI. For example, what should be cached should be cached, the images are in optimal size, the font is not too small etc.
You can use [Google PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) to measure and make a list of TODO tasks.

The [URL path structure](https://moz.com/blog/15-seo-best-practices-for-structuring-urls) is a factor.
To be short,

1. `https://moz.com/blog/15-seo-best-practices-for-structuring-urls` is better than `https://moz.com/blog?id=asasdf`
2. `https://moz.com/blog/` is better than `https://moz.com/public/content/blog`
3. `https://blog.moz.com/` is better than `https://moz.com/blog/`
4. `https://moz.com/blog/15-seo-best-practices-for-structuring-urls` is better than `https://moz.com/blog/15%20seo%20best%20practices%20for%20structuring%20urls`

Social media is hot for SEO. Setting up [Google My Business](https://www.google.com/business/) can have display more information of your website as well as improve the performance on Google. Despite of [Google+](https://plus.google.com/) is dying, it is still believed it can help SEO on Google. Set up an account and get more +1. Meanwhile, Facebook & LinkedIn are also factors but your affords are not counting in algorithm directly (They are counted as backline).

###Understandability of machine
The concept is to follow up-to-date standard and use reasonable tag in HTML, as well as follow [semantic HTML](http://html5doctor.com/lets-talk-about-semantics/). For example, the use of `<h1>`, `<h2>`, `<article>`, `<section>` ... And the most important is to set up unique, meaningful title and meta-description in every pages.

[Title](http://searchenginewatch.com/sew/how-to/2154469/write-title-tags-search-engine-optimization) is a short description of the page. It will be seen Google search engine as well. A easy guild of make a good title is `{Title} - {Name of website}`. For example, `About - Keystone`, `Programmes - Keystones`, `How to Write Title Tags For Search Engine Optimization | SEW`

[Meta-description](http://www.wordstream.com/meta-description) is a slightly longer description which will be displayed in the search result of Google
![Google search result](https://na.cx/i/VoG3kh.png)
The length of the meta-description should be limited to [160 characters](https://moz.com/learn/seo/meta-description). Any longer may trigger punishment by Google.
A good meta-description should include the following characteristics:
1, Understandable by human
2, < 160 characters
3, Repeating keywords (we listed above)
4, Summarise of the content of page

An other [tool](http://seositecheckup.com/) to generate a TODO tasks.

## Design
The key point of designing a searchable website is put enough literal content in every page we want to be searched. We met a problem in [Keystone](Keystoneprep.com) that the index page is only a menu of the site that it basically has no literal content. It makes search engines never gonna reach this page if we don't have meta-description.

## Content
[Refer to this blog post](https://moz.com/beginners-guide-to-content-marketing)

***

## Recommended Task List
1. Unique title nd description for unique pages
2. Minify CSS, JS, Html
3. Gzip
4. Optimize image sizes
5. Eliminate render-blocking CSS
6. Optimize use of Header tag`<h1>` `<h2>`
7. Create Site map, robots.txt
8. Reduce inline CSS
9. Page cache
10. HTML Microdata specifications
11. Reduce HTTP request
12. Site loading time should less than 5 seconds.
13. Set up google analytics
14. Set up google webmaster tool
15. Set up google +, register address and company
16. Add proper alt tags for all images used
17. send 404 status code for page error
18. send 301 status code for page redirect (eg. /services -> /services/ )
19. w3c validation

***

### 1. Unique title nd description for unique pages
```
<meta name="description" content="PAGE DESCRIPTION HERE">
<title>TITLE HERE</title>
```
*Notes: When minifying html code, some tools will remove all `"` in default setting, remember to turn off the this option, otherwise browser will add end quote `"` right before the space character after the first word. e.g. `content="PAGE" DESCRIPTION HERE`.*
### 2. Minify CSS, JS, Html
**Recommended Gulp task:**
#### [Gulp Bundle Assets](https://www.npmjs.com/package/gulp-bundle-assets)

```
var bundle = require('gulp-bundle-assets');
var rename = require('gulp-rename');
var del = require('del');
...
del('./public/bundle/*');
gulp.src('BUNDLE_CONFIG_FILE')
    .pipe(bundle())
    .pipe(gulp.dest('BUNDLE_SOURCE_PATH'))
    .pipe(rename({
      basename: "bundle"
    }))
    .pipe(gulp.dest('BUNDLE_SOURCE_PATH'));
```
#### [Gulp Minify Html](https://www.npmjs.com/package/gulp-minify-html)

*Notes: When minifying html code, some tools will remove all `"` in default setting, remember to turn off the this option, otherwise browser will add end quote `"` right before the space character after the first word. e.g. `content="PAGE" DESCRIPTION HERE`.*
```
var minifyHTML = require('gulp-minify-html');
...
gulp.src('HTML_SOURCE_PATH')
    .pipe(minifyHTML({quotes: true}))
    .pipe(gulp.dest('HTML_DIST_PATH'));
```

#### [Gulp Cssnano](https://www.npmjs.com/package/gulp-cssnano)
```
var cssnano = require('gulp-cssnano');
// var rename = require('gulp-rename');
...
gulp.src('CSS_SOURCE_PATH')
    .pipe(cssnano())
//  .pipe(rename({suffix: '.min'}))
    .pipe(gulp.dest('CSS_DIST_PATH'));
```
#### [Gulp Uglify](https://www.npmjs.com/package/gulp-uglify)
```
var uglify = require('gulp-uglify');
// var rename = require('gulp-rename');
...
gulp.src('JS_SOURCE_PATH')
    .pipe(uglify())
    // .pipe(rename({suffix: '.min'}))
    .pipe(gulp.dest('JS_DIST_PATH'));
```
### 3. Gzip
1. Edit Nginx.conf file
```
sudo  vim /etc/nginx/nginx.conf
```
2. In Block `http{}` find and delete any Gzip setting
3. Paste the following code and save
```
  # Compression
  gzip on;
  gzip_http_version  1.1;
  gzip_comp_level    5;
  gzip_min_length    256;
  gzip_proxied       any;
  gzip_vary          on;

  # Compress all output labeled with one of the following MIME-types.
  gzip_types
    application/atom+xml
    application/javascript
    application/json
    application/rss+xml
    application/vnd.ms-fontobject
    application/x-font-ttf
    application/x-web-app-manifest+json
    application/xhtml+xml
    application/xml
    font/opentype
    image/svg+xml
    image/x-icon
    text/css
    text/plain
    text/javascript
    text/x-component;
  # text/html is always compressed by HttpGzipModule
```
4. Restart Nginx Server
```
sudo service nginx restart
```
5. Check if Gzip enabled
```
curl --header "Accept-Encoding: gzip,deflate,sdch" -I http://domain.com
```
You should see `Content-Encoding: gzip`. If Gzip is not enabled, check if you website have set the Content Header as `text/html`. You should see `Content-Type: text/html` if yes, otherwise, set the Content Header as `text/html`.

### 4. Optimize image sizes
#### [Gulp Cssnano](https://www.npmjs.com/package/gulp-cssnano)
```
var imagemin = require('gulp-imagemin');
...
gulp.src('IMAGE_SOURCE_PATH')
    .pipe(imagemin({optimizationLevel: 5}))
    .pipe(gulp.dest('IMAGE_DIS_PATH'));
});
```
### 5. Eliminate render-blocking CSS
Put the `<link href="main.css" property="stylesheet" rel="stylesheet">` to the bottom of the body, if you think the website looks ugly before css file loaded, try copy some necessary code, e.g. Header/Nav bar/Common tag style, minify it and put it inside `<head>`.
### 6. Optimize use of Header tag `<h1>` `<h2>`
Avoid using `<h1>` and `<h2>` for meaningless sentence, e.g. 'Thank you!' and 'Welcome!'
### 7. Create Site map, robots.txt
You can create a standard sitemap.xml by Online tool, e.g. [Xml Sitemaps](https://www.xml-sitemaps.com/). You should place your sitemap.xml in Domain Root, so as http://domain.com/sitemap.xml.

New a file named `robots.txt` for search engine knows the allow page and denied page to visit. You should place your robots.txt in Domain Root, so as http://domain.com/robots.txt. Sample of a robots.txt file:
```
Sitemap: http://altitudelabs.com/sitemap.xml
User-agent:*
```

### 8. Reduce inline CSS
Search for `style=` in your templates or views folder, try code those items in stylesheet and remove all inline CSS.
### 9. Page cache
Sample nginx server profile:
```
proxy_cache_path /var/keystone/cache levels=1:2 keys_zone=keystone_cache:10m max_size=10g inactive=60m;

server {
    listen 80;
    server_name www.keystoneprep.com;
    location /{
        expires 1h;

        proxy_pass http://127.0.0.1:8888;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
   }
}
```
To Check if Cache is enabled, goto the website and open Network tab in Chrome. You should see status 304 (Not-Modified) after reloading the page again.
### 10. HTML Microdata specifications
Reference: https://developers.google.com/structured-data/schema-org?hl=en

*Notes: It may not suitable for website which is not data-intensive.*
### 11. Reduce HTTP request
*You can check the number of HTTP request with Nework tab in Chrome Developer Tools.
HTTP request should be less than **20** when page loaded.*
Task Which may help
* [Gulp Bundle Assets](https://www.npmjs.com/package/gulp-bundle-assets)
* Image Sprite
* Load unnecessary script file after Page Load
```
var loadScript = function(e, t) {
    var a = document.createElement("script"),
        n = !1;
    a.type = "text/javascript", a.async = !0, a.src = e, a.onload = a.onreadystatechange = function() {
        n || this.readyState && "complete" != this.readyState || (n = !0, t())
    };
    var o = document.getElementsByTagName("script")[0];
    o.parentNode.insertBefore(a, o)
};
loadScript("/*Script File*/", function() {
    ! function(e) {
        //Code after source file loaded
    }(jQuery);
    jQuery.noConflict(!0)
});
```

### 12. Site loading time should less than 5 seconds.
Set it as the target after doing all tasks.
Reference: [Google Page Insights](https://developers.google.com/speed/pagespeed/insights/)
### 13. Set up google analytics
[Google Analytics](http://www.google.com/analytics/)
### 14. Set up google webmaster tool
[Google Webmaster Tool](http://www.google.com/webmasters/)
### 15. Set up google + page, register address and company
[Google+](https://plus.google.com)
To setup a Google+ Page for a company, Google need an address to verify the ownership of the company.
### 16. Add proper alt tags for all images used
`<img src="" alt="ALTERNATIVE TEXT HERE">`
### 17. send 404 status code for page error
For express:
```
    res.status(404);
```
If it success, you should see 404 status in Network Tab in Chrome Developer Tools.
### 18. send 301 status code for page redirect (eg. /services -> /services/ )
For express:
```
    res.status(301);
    res.redirect('/ORIGINAL_PAGE');
```
and also make sure to do 301 redirect for domain ip address in /etc/nginx/sites-available/site
```
    server {
        listen 80;
        server_name 54.179.128.50 www.altitudelabs.com;
        return 301 $scheme://altitudelabs.com$request_uri;
    }
```
and then
```
sudo rm /etc/nginx/sites-enabled/site
sudo ln -s /etc/nginx/sites-available/site /etc/nginx/sites-enabled/site
sudo service nginx restart
```
If it success, you should see 301 status in Network Tab in Chrome Developer Tools.

### 19. W3c validation
Reference: http://validator.w3.org/
