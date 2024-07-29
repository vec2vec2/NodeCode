## moonwalk - 一个快速简洁的博客主题，具有干净的黑暗模式

![截图](https://raw.githubusercontent.com/abhinavs/moonwalk/master/_screenshots/moonwalk.png)

<h3 align="center">
  <img src="https://raw.githubusercontent.com/abhinavs/moonwalk/master/logo.png" width="24"/>
<a href="https://abhinavs.github.io/moonwalk/">尝试演示</a>
</h3>

## 特点
* 具有主题切换的浅色和深色模式
* 垂直列表、水平列表、卡片列表
* 带有导航栏、页脚和作品集的登陆页面
* 快速（极少CSS）- 性能、可访问性、最佳实践和SEO评分均为100/100，详见 [Lighthouse 报告](https://raw.githubusercontent.com/abhinavs/moonwalk/master/_screenshots/lighthouse-report.png)
* 响应式和移动友好
* SEO优化（使用 [Jekyll Soopr SEO Tag](https://github.com/jekyll/jekyll-soopr-seo-tag)）
* RSS订阅（使用 [Jekyll Feed](https://github.com/jekyll/jekyll-feed)）
* 易于扩展
* 完全兼容 [GitHub Pages](https://pages.github.com/)（参见 [GitHub Pages 安装](#github-pages-installation)）
* 自动生成社交媒体分享图片（使用 [Soopr](https://www.soopr.co)）
* 分享和点赞按钮（使用 [Soopr](https://www.soopr.co)）

#### Lighthouse

![Lighthouse 报告](https://raw.githubusercontent.com/abhinavs/moonwalk/master/_screenshots/lighthouse-report.png)

## 快速安装
1. [Fork 此仓库](https://github.com/abhinavs/moonwalk/fork)。
2. `cd moonwalk`
3. `bin/bootstrap`
4. [可选] 注册 Soopr，并在 `_config.yml` 文件中添加你的 `publish_token`。

如果你在Windows上安装Moonwalk，可能需要使用 Ruby 3.0.x 而不是 Ruby 3.1.x - 你可以在 [这里](https://github.com/abhinavs/moonwalk/blob/master/moonwalk_on_windows.md) 查看Windows特定的安装说明。

## 启动服务器
`bin/start` - 开发服务器将启动于 http://127.0.0.1:4000

## 部署
Moonwalk 可以轻松部署在所有云服务提供商（如AWS）以及静态网站托管服务（如Netlify和Vercel）上。你也可以使用此按钮一键部署：
<br />
<br />
[![Deploy with Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abhinavs/moonwalk)

如果你想将 Moonwalk 用作 gem 或使用 Github Pages，请参见 [此页面](https://github.com/abhinavs/moonwalk/blob/master/github_pages.md)。

## 自定义

你可以编辑 `_config.yml` 文件以自定义你的博客。你可以更改博客名称、作者、主题外观（浅色、深色或自动）、日期格式等。自定义字段应该很容易理解， `_config.yml` 包含一些注释帮助你理解每个字段的作用。

有关进一步的自定义（例如布局、CSS），请参见 [Jekyll 官方文档](https://jekyllrb.com/docs/themes/#overriding-theme-defaults) 中的自定义主题部分。

### 自定义菜单

为了在首页中添加、编辑或删除条目，你可以复制 `_data` 文件夹内的 `home.yml` 文件。通过该文件，你可以定义菜单的结构，并添加导航栏、页脚、作品集的数据，或者简单地删除所有这些，使用简单的博客布局。查看默认配置以了解其工作原理，并继续阅读以获得更全面的解释。

`home.yml` 文件接受以下字段：

1. 垂直列表
  - `entries` 定义一个新的无序列表，将包含菜单条目
  - 每个条目在行首标记 `-`
  - 每个条目有以下属性：
    - `title` 定义该菜单条目渲染的文本
    - `url` 可以是URL或`false`。如果为`false`，条目将渲染为纯文本；否则，条目将渲染为指向指定URL的链接。URL可以是相对的或绝对的。
    - `post_list` 可以为 `true` 或 `false`。如果为 true，该条目将包含网站中的所有文章作为子条目。这用于渲染你的文章列表。
    - `entries` 是的，你可以在条目内有条目。这样你可以创建嵌套的子列表！
2. 卡片列表 - 卡片用于展示作品集项目。请参见 `_data/home.yml` 文件中的 `project_entries`
  - 每个条目在行首标记 `-`
  - 每个条目有以下属性：
    - `title` 定义卡片的标题
    - `desc` 是卡片的正文
    - `url` 是此卡片可以指向的相对或绝对链接。
    - `highlight` 如果你想强调某些内容，请保持文本简短
3. 水平列表 - moonwalk 使用水平列表创建导航栏和页脚。请参见 `data/home.yml` 文件中的 `navbar_entries` 和 `footer_entries`
  - 每个条目在行首标记 `-`
  - 每个条目有以下属性：
    - `title` 定义卡片的标题
    - `url` 是此卡片可以指向的相对或绝对链接。

### 专业提示
1. Moonwalk 有 3 种内置布局：
  - post - 用于内容
  - blog - 用于列出博客文章
  - home - 用于登陆页面
  你可以将 `index.md` 文件更改为使用 home 或 blog 布局。

2. 调整配色方案非常简单。
  - 对于浅色模式，自定义这些 css 变量
```css
html {
    --bg: #fff;
    --bg-secondary: #f3f4f6;
    --headings: #1e293b;
    --text: #374151;
    --text-secondary: #6b7280;
    --links: #6366f1;
    --highlight: #ffecb2; // 浅黄色
    --code-text: #9d174d;
}
```
  - 对于深色模式，自定义这些 css 变量
```css
@mixin dark-appearance {
  html, body  {
      --headings: #74c0fc;
      --links: #91a7ff;
      --highlight: #41c7c7;
      --bg: #1f242a;
      --bg-secondary: #323945;
      --text: #adb5bd;
      --text-secondary: #9ca3af;
      --code-text: #91a7ff;
  };
}
```
3. 在 [Soopr](https://www.soopr.co) 上免费注册，并在 `_config.yml` 文件中添加你的 `publish_token` - 这样，每个页面都会有短URL、点赞按钮和自动生成的社交媒体分享图片。

![Twitter 卡片](https://raw.githubusercontent.com/abhinavs/moonwalk/master/_screenshots/twitter_card.png)

## 贡献

欢迎在 GitHub 上报告 Bug 和提交 Pull Request：https://github.com/abhinavs/moonwalk。

## 开发

要设置开发此主题的环境，请运行 `bundle install`。

你的主题设置与普通的 Jekyll 站点一样！要测试你的主题，请运行 `bundle exec jekyll serve` 并在浏览器中打开 `http://localhost:4000`。像正常一样添加页面、文档、数据等以测试你的主题内容。当你对主题和内容进行修改时，你的站点将重新生成，并且在刷新后应该在浏览器中看到更改，就像正常一样。

当你的主题发布时，只有 `_layouts`、`_includes`、`_sass` 和 `assets` 中 Git 跟踪的文件会被打包。
要将自定义目录添加到你的主题 gem 中，请相应地编辑 `moonwalk.gemspec` 中的正则表达式。

## 致谢
这个主题的原始基础是 [no style please!](https://github.com/riggraz/no-style-please) 主题，由 [Riccardo Graziosi](https://riggraz.dev/) 创建 - 非常感谢他创建了一个几乎没有CSS的精彩主题。

## 许可证

根据 [MIT 许可证](https://opensource.org/licenses/MIT) 提供开源的主题。

## 其他项目
如果你喜欢 Moonwalk，请查看我的其他项目
*   [cookie](https://github.com/abhinavs/cookie) - 使用 Jekyll 和 Tailwind CSS 的免费着陆网站模板
*   [scoop](https://github.com/abhinavs/scoop) - 使用 Corneal、ActiveRecord、Capistrano、Puma 和 Nginx 的 Sinatra 模板项目
*