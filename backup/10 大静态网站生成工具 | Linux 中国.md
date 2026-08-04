Title: 10 大静态网站生成工具 | Linux 中国

URL Source: https://zhuanlan.zhihu.com/p/260957368

Markdown Content:
> 在寻找部署静态网页的方法吗？这几个开源的静态网站生成工具可以帮你迅速部署界面优美、功能强大的静态网站，无需掌握复杂的 HTML 和 CSS 技能。

*   来源：[https://linux.cn/article-12671-1.html](https://link.zhihu.com/?target=https%3A//linux.cn/article-12671-1.html)
*   作者：Ankush Das
*   译者：Xiaobin.Liu

_（本文字数：3396，阅读时长大约：5 分钟）_

> 在寻找部署静态网页的方法吗？这几个开源的静态网站生成工具可以帮你迅速部署界面优美、功能强大的静态网站，无需掌握复杂的 HTML 和 CSS 技能。

静态网站是什么？
--------

技术上来讲，静态网站是指网页不是由服务器动态生成的。HTML、CSS 和 JavaScript 文件就静静地躺在服务器的某个路径下，它们的内容与终端用户接收到的版本是一样的。原始的源码文件已经提前编译好了，源码在每次请求后都不会变化。

[Linux.CN](https://link.zhihu.com/?target=http%3A//linux.cn/) 是一个依赖多个数据库的动态网站，当有浏览器的请求时，网页就会生成并提供服务。大部分网站是动态的，你与这些网站互动时，大量的内容会经常改变。

静态网站有一些好处，比如加载时间更短，请求的服务器资源更少、更安全（值得商榷）。

传统上，静态网站更适合于创建只有少量网页、内容变化不频繁的小网站。

然而，随着静态网站生成工具出现后，静态网站的适用范围越来越大。你还可以使用这些工具搭建博客网站。

我整理了几个开源的静态网站生成工具，这些工具可以帮你搭建界面优美的网站。

最好的开源静态网站生成工具
-------------

请注意，静态网站不会提供很复杂的功能。如果你需要复杂的功能，那么你可以参考适用于动态网站的[最佳开源 CMS](https://link.zhihu.com/?target=https%3A//itsfoss.com/open-source-cms/)列表。

**1、Jekyll**

![Image 1: a website with a black and yellow design](https://pic1.zhimg.com/v2-3e124971259bcc034851e4ae855b9e88_b.jpg)

Jekyll 是用 [Ruby](https://link.zhihu.com/?target=https%3A//www.ruby-lang.org/en/) 写的最受欢迎的开源静态生成工具之一。实际上，Jekyll 是 [GitHub 页面](https://link.zhihu.com/?target=https%3A//pages.github.com/) 的引擎，它可以让你免费用 GitHub 托管网站。

你可以很轻松地跨平台配置 Jekyll，包括 Ubuntu。它利用 [Markdown](https://link.zhihu.com/?target=https%3A//github.com/Shopify/liquid/wiki)、[Liquid](https://link.zhihu.com/?target=https%3A//github.com/Shopify/liquid/wiki)（模板语言）、HTML 和 CSS 来生成静态的网页文件。如果你要搭建一个没有广告或推广自己工具或服务的产品页的博客网站，它是个不错的选择。

它还支持从常见的 CMS（ _内容管理系统(Content management system)_）如 Ghost、WordPress、Drupal 7 迁移你的博客。你可以管理永久链接、类别、页面、文章，还可以自定义布局，这些功能都很强大。因此，即使你已经有了一个网站，如果你想转成静态网站，Jekyll 会是一个完美的解决方案。你可以参考[官方文档](https://link.zhihu.com/?target=https%3A//jekyllrb.com/docs/)或 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/jekyll/jekyll)了解更多内容。

**2、Hugo**

![Image 2: hugo - the world's fastest framework for building websites](https://pic2.zhimg.com/v2-78809367b597167c3197c63bdef0e3ad_b.jpg)

Hugo 是另一个很受欢迎的用于搭建静态网站的开源框架。它是用 [Go 语言](https://link.zhihu.com/?target=https%3A//golang.org/)写的。

它运行速度快、使用简单、可靠性高。如果你需要，它也可以提供更高级的主题。它还提供了一些有用的快捷方式来帮助你轻松完成任务。无论是组合展示网站还是博客网站，Hogo 都有能力管理大量的内容类型。

如果你想使用 Hugo，你可以参照它的[官方文档](https://link.zhihu.com/?target=https%3A//gohugo.io/getting-started/)或它的 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/gohugoio/hugo)来安装以及了解更多相关的使用方法。如果需要的话，你还可以将 Hugo 部署在 GitHub 页面或任何 CDN 上。

**3、Hexo**

![Image 3: a black screen with the words fast simple 6 powerful blog framework](https://pic1.zhimg.com/v2-c41ab3ff1bef1e59dccc65276eb92814_b.jpg)

Hexo 是一个有趣的开源框架，基于 [Node.js](https://link.zhihu.com/?target=https%3A//nodejs.org/en/)。像其他的工具一样，你可以用它搭建相当快速的网站，不仅如此，它还提供了丰富的主题和插件。

它还根据用户的每个需求提供了强大的 API 来扩展功能。如果你已经有一个网站，你可以用它的[迁移](https://link.zhihu.com/?target=https%3A//hexo.io/api/migrator.html)扩展轻松完成迁移工作。

你可以参照[官方文档](https://link.zhihu.com/?target=https%3A//hexo.io/docs/)或 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/hexojs/hexo) 来使用 Hexo。

**4、Gatsby**

![Image 4: the modern way to build the web](https://pic4.zhimg.com/v2-ac67d3fcbb0e4fc2c7743417d1c18a83_b.jpg)

Gatsby 是一个越来越流行的开源网站生成框架。它使用 [React.js](https://link.zhihu.com/?target=https%3A//reactjs.org/) 来生成快速、界面优美的网站。

几年前在一个实验性的项目中，我曾经非常想尝试一下这个工具，它提供的成千上万的新插件和主题的能力让我印象深刻。与其他静态网站生成工具不同的是，你可以使用 Gatsby 生成一个网站，并在不损失任何功能的情况下获得静态网站的好处。

它提供了与很多流行的服务的整合功能。当然，你可以不使用它的复杂的功能，或将其与你选择的流行 CMS 配合使用，这也会很有趣。你可以查看他们的[官方文档](https://link.zhihu.com/?target=https%3A//www.gatsbyjs.com/docs/)或它的 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/gatsbyjs/gatsby)了解更多内容。

**5、VuePress**

![Image 5: vuepress is a static site generator](https://pic4.zhimg.com/v2-0eccfd14317abcdaaee191e5d673ef37_b.jpg)

VuePress 是由 [Vue.js](https://link.zhihu.com/?target=https%3A//vuejs.org/) 支持的静态网站生成工具，而 Vue.js 是一个开源的渐进式 JavaScript 框架。

如果你了解 HTML、CSS 和 JavaScript，那么你可以无压力地使用 VuePress。你应该可以找到几个有用的插件和主题来为你的网站建设开个头。此外，看起来 Vue.js 的更新一直很活跃，很多开发者都在关注 Vue.js，这是一件好事。

你可以参照他们的[官方文档](https://link.zhihu.com/?target=https%3A//vuepress.vuejs.org/guide/)和 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/vuejs/vuepress)了解更多。

**6、Nuxt.js**

![Image 6: the intuitive vue framework](https://pic2.zhimg.com/v2-6ba6b1e24ad26aaa89d249ac9e2b7f7d_b.jpg)

Nuxt.js 使用了 Vue.js 和 Node.js，但它致力于模块化，并且有能力依赖服务端而非客户端。不仅如此，它的目标是为开发者提供直观的体验，并提供描述性错误，以及详细的文档等。

正如它声称的那样，在你用来搭建静态网站的所有工具中，Nuxt.js 可以做到功能和灵活性两全其美。他们还提供了一个 [Nuxt 线上沙盒](https://link.zhihu.com/?target=https%3A//template.nuxtjs.org/)，让你不费吹灰之力就能直接测试它。

你可以查看它的 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/nuxt/nuxt.js)和[官方网站](https://link.zhihu.com/?target=https%3A//nuxtjs.org/)了解更多。

**7、Docusaurus**

![Image 7: docusa makes it easy to maintain open source documentation websites](https://pic4.zhimg.com/v2-9d59d53e754da4860d24cd52f7e24a23_b.jpg)

Docusaurus 是一个有趣的开源静态网站生成工具，为搭建文档类网站量身定制。它还是 [Facebook 开源计划](https://link.zhihu.com/?target=https%3A//opensource.facebook.com/)的一个项目。

Docusaurus 是用 React 构建的。你可以使用所有的基本功能，像文档版本管理、文档搜索和翻译大多是预先配置的。如果你想为你的产品或服务搭建一个文档网站，那么可以试试 Docusaurus。

你可以从它的 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/facebook/docusaurus)和它的[官网](https://link.zhihu.com/?target=https%3A//docusaurus.io/)获取更多信息。

**8、Eleventy**

![Image 8: 11ty logo on a black background](https://pic3.zhimg.com/v2-79fc7248f8f25a9e194ce88dd0851b9e_b.jpg)

Eleventy 自称是 Jekyll 的替代品，旨在以更简单的方法来制作更快的静态网站。

它似乎很容易上手，而且它还提供了适当的文档来帮助你。如果你想找一个简单的静态网站生成工具，Eleventy 似乎会是一个有趣的选择。

你可以参照它的 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/11ty/eleventy/)和[官网](https://link.zhihu.com/?target=https%3A//www.11ty.dev/)来了解更多的细节。

**9、Publii**

![Image 9: static css with guu build an extremely fast html website](https://pic2.zhimg.com/v2-fc973850c95e6cdf07955cff7c340d0d_b.jpg)

Publii 是一个令人印象深刻的开源 CMS，它能使生成一个静态网站变得很容易。它是用 [Electron](https://link.zhihu.com/?target=https%3A//www.electronjs.org/) 和 Vue.js 构建的。如果有需要，你也可以把你的文章从 WorkPress 网站迁移过来。此外，它还提供了与 GitHub 页面、Netlify 及其它类似服务的一键同步功能。

如果你利用 Publii 生成一个静态网站，你还可以得到一个所见即所得的编辑器。你可以从[官网](https://link.zhihu.com/?target=https%3A//getpublii.com/)下载它，或者从它的 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/GetPublii/Publii)了解更多信息。

**10、Primo**

![Image 10: the homepage of a coffee shop](https://pic1.zhimg.com/v2-d465add9a41a5ad0a5eefea6a8ff3480_b.jpg)

一个有趣的开源静态网站生成工具，目前开发工作仍很活跃。虽然与其他的静态生成工具相比，它还不是一个成熟的解决方案，有些功能还不完善，但它是一个独特的项目。

Primo 旨在使用可视化的构建器帮你构建和搭建网站，这样你就可以轻松编辑和部署到任意主机上。

你可以参照[官网](https://link.zhihu.com/?target=https%3A//primo.af/)或查看它的 [GitHub 页面](https://link.zhihu.com/?target=https%3A//github.com/primo-app/primo-desktop)了解更多信息。

结语
--

还有很多文章中没有列出的网站生成工具。然而，我试图提到最好的静态生成器，为您提供最快的加载时间，最好的安全性和令人印象深刻的灵活性。

列表中没有你最喜欢的工具？在下面的评论中告诉我。

* * *

via: [https://itsfoss.com/open-source\-static-site-generators/](https://link.zhihu.com/?target=https%3A//itsfoss.com/open-source-static-site-generators/)

作者：[Ankush Das](https://link.zhihu.com/?target=https%3A//itsfoss.com/author/ankush/) 选题：[lujun9972](https://link.zhihu.com/?target=https%3A//github.com/lujun9972) 译者：[lxbwolf](https://link.zhihu.com/?target=https%3A//github.com/lxbwolf) 校对：[wxy](https://link.zhihu.com/?target=https%3A//github.com/wxy)

本文由 [LCTT](https://link.zhihu.com/?target=https%3A//github.com/LCTT/TranslateProject) 原创编译，[Linux中国](https://link.zhihu.com/?target=https%3A//linux.cn/) 荣誉推出