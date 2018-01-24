# jMonkeyEngine 中文文档

[![Build Status][1]][2]

本项目用于存储、编辑、生成 [jMonkeyEngine][3] 的中文文档。

* [jME3中文维基][4]
* [jME3中文首页][5]

你可以通过下列方式来编辑[此文档][6]：

* 通过github在线编辑 (点击页面上方的Edit按钮，编辑后提交合并请求)。
* 使用 `git clone` 把文档保存到本地，再然后离线编辑。
* 使用 Atom 离线编辑，详见[使用 Atom 编辑维基][7]。

## 前置需求

* 拥有 github.com 账号。
* 可选：成为wiki项目成员。

如果你不是该项目的成员，可以先把它复刻(fork)到你自己的 Github 仓库。在自己的分支中编辑后， 再向 jmecn/wiki 项目发起合并请求(“Pull Request”)，通过这种方式来贡献内容。

把 wiki 仓库复刻(fork)到你自己的Github账号：

* 打开 https://github.com/jmecn/wiki 页面。
* 在页面顶部的菜单中，点击 **Fork** 按钮。

本 wiki 使用 Asciidoc 语法编写文档，语法参考如下：

* [Asciidoc Syntax Quick Reference][8]
* [Asciidoctor User Manual][9]

关于 git 命令的用法，请参考：

* [git - the simple guide][10]


## 贡献

在贡献wiki内容时，有几条简单的规则需要遵守。

* 最好在[jMonkeyEngine 论坛][11]的`Documentation`话题下发帖，告知其他人你提交了一个PR。
* 在创建wiki页面时，请确保页头属性的完整性。详见：[Wiki页头分析][12]
* 在连接到其它wiki页面时，总是使用 "内部文档交叉引用"。格式`<<path/to/wiki/page#,自定义标签>>`。
* 在插入图片时，先把图片保存到 wiki 的 image 目录下，然后通过 `image` 前缀链接到该文件，并在文件路径后使用 `[]` 注明图片参数。

**“内部文档交叉引用”说明：**

格式：`<<path/to/wiki/page#,自定义标签>>`

例如：链接到“开发需求”页面 - `<<engine/requirements#,开发需求>>`

* `#`号表示文件后缀。这种链接在工作时，首先会查找对应的`.adoc`文件，找不到的话会自动选择对应的`.html`版本。
* 采用相对路径，相对于 `asciidoc` 目录。
* 该链接指向 `requirements.adoc` 页面，位于 `asciidoc` 目录下的 `engine` 子目录中。

更多关于“内部文档交叉引用”的信息，请参考：[http://asciidoctor.org/docs/user-manual/#inter-document-cross-references][13]

**插入图片说明：**

格式： `image::path/to/image.jpg[image alt text,width=" ",height=" ", align=" "]`

例如：单行图片 - `image::beginner/beginner-assets-models.png[beginner-assets-models.png,320,250,align="center"]`

*  该图片独占一行。
*  图片文件保存在 `images` 目目录下的 `beginner` 子文件夹中。
*  文件名为 `beginner-assets-models.png`。
*  图片的提示文字 `alt text` 为 `beginner-assets-models.png`。
*  图片宽度为320像素。
*  图片高度为250像素。
*  图片居中对齐。

** 如果你想在段落行内插入图片，应该使用 `image:` 前缀。(注意只有一个冒号) **

更多关于插入图片的详细说明，请参考：[http://asciidoctor.org/docs/user-manual/#images][14]


## 编译

本项目使用 Gradle 脚本自动编译，执行下面的编译任务即可。

```shell
 $ ./gradlew asciidoctor
```

编译结果保存在build目录中，在浏览器中打开 *build/asciidoc/html5/index.html*  文件即可查看生成的html页面。

在 Atom 编辑器中，你可以安装 `Asciidoc Preview` 插件，实时查看生成的html文档，不需要进行编译。

## TODO

- [x] configure travis build
- [x] configure github + gradle + travis to publish on gh-pages branches
- [x] find and fixe conversion bug
- [x] complete conversion: note, warning, ...
- [x] fix warning during html's generation (should be fixed manually)
- [x] add meta info during conversion (doctitle, revision, tags, ...)
- [x] add a home page (index.html)
- [ ] add a navigation bar or a menu (?)
- [ ] customize html layout (header, footer, css)
- [x] transfer ownership to jMonkeyEngine org
- [x] complete Doc, how to contribute,...
- [ ] accept Pull Request
- [ ] write a post about the migration (the tools, why asciidoc, vs alternatives, how ...)
- [ ] generate sitemap
- [x] add search box
- [ ] add google analytics (?)
- [ ] support emoji
- [ ] support iframe block
- [x] fix slideshow of "Xxx for Dummies"
- [ ] optimize remove useless images
- [ ] optimize image, use smaller file, eg convert to jpg or to webp, resize
- [ ] organize i18n / lang
- [ ] use tags to create taxonomy


[1]:https://travis-ci.org/jmecn/wiki.svg?branch=master
[2]:https://travis-ci.org/jmecn/wiki
[3]:http://jmonkeyengine.org/
[4]:https://jmecn.github.io/wiki/
[5]:https://jmecn.github.io/
[6]:https://github.com/jmecn/wiki/tree/master/src/docs/asciidoc
[7]:https://jmecn.github.io/wiki/contribution/wiki/atom_editor.html
[8]:http://asciidoctor.org/docs/asciidoc-syntax-quick-reference/
[9]:http://asciidoctor.org/docs/user-manual/#introduction-to-asciidoctor
[10]:http://rogerdudler.github.io/git-guide/
[11]:https://hub.jmonkeyengine.org/
[12]:https://jmecn.github.io/wiki/contribution/wiki/wiki_header.html
[13]:http://asciidoctor.org/docs/user-manual/#inter-document-cross-references
[14]:http://asciidoctor.org/docs/user-manual/#images
