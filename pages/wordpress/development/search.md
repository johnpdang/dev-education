# Search

{% embed url="https://wedevs.com/133739/add-search-bar-in-wordpress/" %}

## How to Add A Search Bar in WordPress within Minutes

A search bar is very important for your website. Your website visitors can find whatever they need in a moment using it. Basically, a search box is the Google of your website that lets your users find important things quickly. This post is about the easiest ways to create a search bar in WordPress sites.

In most of the WordPress themes, a search panel is included by default. But if any theme doesn't have it or you want to make your own custom search box, you can easily do that too. WordPress is well renowned for its customizability so there are different procedures to add a search bar to your website. Let's do it together.

### Methods of Adding A Search Bar

WordPress itself has the search option as a widget. Moreover, there are lots of plugins which may help you to add a search panel or you can create one on your own. All these three methods are mentioned here step-by-step along with the images.

#### From the Widget Panel

This is the easiest and fastest way to bring the search bar to your site. All you need is to head towards the WordPress widgets.

* Go to your **Admin Dashboard**.
* Navigate to **Appearance &gt; Widgets.** Here, you'll find the widget named **Search** under the **Available Widgets.** ![](https://wedevs.s3.amazonaws.com/uploads/2018/07/chrome_2018-07-24_09-49-02-1.png)
* Click on it and then hit the **Add Widget** button. You can also drag it to the **Widget Area**. You can add the title for your search widget if required. ![](https://wedevs.s3.amazonaws.com/uploads/2018/07/chrome_2018-07-24_10-03-06.png)
* Now go to your site and you'll see the Search widget on the sidebar. ![](https://wedevs.s3.amazonaws.com/uploads/2018/07/chrome_2018-07-24_12-37-56.png)

#### With The Help of A Plugin

This is also an automated method. You won't need coding or technical knowledge at all.

* Go to **Plugins &gt; Add New.**
* Search for a plugin that adds the search bar. E.g., we started typing ‘add search' and this list appeared; We installed the **Add Search To Menu** plugin for this tutorial. ![](https://wedevs.s3.amazonaws.com/uploads/2018/07/chrome_2018-07-23_17-55-10.png)
* Install the plugin and then activate it.
* Use the **Settings &gt; Add Search To Menu** to configure the plugin.

#### Manually Add A Search Box \(For Advanced Users\)

This is where you'll need a bit of technical knowledge. As a result, you'll get the full control of customization and styling.

* Open the _header.php_ or _sidebar.php_ file \(where you want to add the search button\).
* Just add this function _&lt;?php get\_search\_form\(\); ?&gt;_ in your code. It will call the search form from your _searchform.php_ template. If there is no _searchform.php_ file, don't worry. It will create one by default.
* Go to your homepage and you'll see the Search box in the side menu \(if you'd added the function in _sidebar.php_\) or in the upper panel \(if you'd added the function in _header.php_\). ![](https://wedevs.s3.amazonaws.com/uploads/2018/07/chrome_2018-07-24_11-35-24.png)
* If you want to customize the style of this box, open _style.css_ file and customize the _search-form_ position, size or styling according to your choice. ![](https://wedevs.s3.amazonaws.com/uploads/2018/07/2018-07-24_11-47-51.png)

Long story short, WordPress is pretty easy to use and customize. We've discussed three different ways of adding a Search bar here. Go whichever way you want. Enjoy!

