# ghost-codek
### a fork from [ghost-wbkd](https://github.com/wbkd/ghost-wbkd)

![screenshot](https://raw.githubusercontent.com/manhhailua/ghost-codek/master/screenshot.png)

**See it live on [my blog](http://codek.org)**

### Theme features

* `About` sidebar show different content by blog|post|page|tag description
* Code highlighting by [prism.js](https://github.com/PrismJS/prism)

### Upcoming features

* `Subscribe` sidebar
* Responsive to mobile for main navigation
* `Random articles` sidebar
* `Related articles` sidebar to currently viewing post
* Post auto navigation sidebar

Request for a feature? Submit an issue [here](https://github.com/manhhailua/ghost-codek/issues).

### Install

To install the theme, clone this repository into your theme folder of your ghost installation:

```
$ cd path-to-ghost/content/themes
$ git clone https://github.com/manhhailua/ghost-codek.git
```

After that, restart the blog and select the `codek-{version}` theme in your ghost admin panel.

### Customize

Due to restrictions of the Ghost templates, some values are hard-coded at the moment. To customize the theme, you have to edit the Handlebars templates in the theme folder.

**Disqus**

To enable the Disqus comment module, you have to add you Disqus username in the ```post.hbs``` file:

```
var disqus_shortname = 'example'; // required: replace example with your forum shortname
```


**Navigation**

For changing the navigation links and labels, you have to edit the ```partials/navigation.hbs``` file.

```
<!--Uncomment this to customize the navigation manually-->
<!--<div class="taglist-wrapper clearfix">-->
  <!--<ul id="taglist" class="taglist">-->
    <!--<li><a href="{{@blog.url}}">Home</a></li>-->
    <!--<li><a href="/tag/javascript">javascript</a></li>-->
    <!--<li><a href="/tag/nodejs">nodejs</a></li>-->
    <!--<li><a href="/tag/data-visualization">data visualization</a></li>-->
    <!--<li><a href="/tag/d3">d3</a></li>-->
    <!--<li><a href="/tag/maps">maps</a></li>-->
  <!--</ul>-->
<!--</div>-->

<!--This is for default navigation-->
<ul id="taglist" class="taglist">
  {{#foreach navigation}}
    <li><a href="{{url}}">{{label}}</a></li>
  {{/foreach}}
</ul>
```

**Sidebar Widgets**

There are three widgets in the sidebar: About, Social and Latest Articles. The latest articles are pulled automatically from the RSS-Feed of your page. If you want to change the url of your RSS-Feed, you have to edit the ```assets/js/webkid.js``` file.

The other two widgets are configured in the ```partials/sidebar.hbs``` template.

```
<!--Change this to your homepage-->
<p>See our latest posts at <a href="http://codek.org">codek.org</a></p> (for Vietnamese only)

<!--Change the links to your sites or use default setting-->
<div class="sidebox box social clearfix">
  <ul>
    <li><a href="/rss" target="_blank" class="social-item rss"><i class="fa fa-rss"></i></a></li>
    <li><a href="{{facebook_url}}" target="_blank" class="social-item facebook"><i class="fa fa-facebook"></i></a></li>
    <li><a href="{{twitter_url}}" target="_blank" class="social-item tw"><i class="fa fa-twitter"></i></a></li>
    <li><a href="{{@blog.url}}" target="_blank" class="social-item home"><i class="fa fa-home"></i></a></li>
  </ul>
</div>
```

**Code highlighting**

To use prism.js style for code block markdown, add `language-xxxx` (`xxxx` equal to language to be highlighted) next to the opening ` ``` `.

```
 ```language-markup
 <h1>Hello World!</h1>
 ```
```

Change below line of code in `default.hbs` to switch to expected highlighting style. Choose your prefered prism theme.

```
<link rel="stylesheet" type="text/css" href="{{asset "bower_components/prism/themes/prism-tomorrow.css"}}"/>
```

### Authors

[Manh Pham](https://www.facebook.com/manhhailua) of [codek.org](http://codek.org)
