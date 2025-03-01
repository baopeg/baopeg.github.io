 # Hexo Front-matter Parameters

## Post Front-matter

| Parameter                  | Explanation                                                                                                 | Required |
|----------------------------|-------------------------------------------------------------------------------------------------------------|----------|
| title                      | 【必需】文章标题                                                                                            | Yes      |
| date                       | 【必需】文章创建日期                                                                                        | Yes      |
| updated                    | 【可选】文章更新日期                                                                                        | No       |
| tags                       | 【可选】文章标签                                                                                            | No       |
| categories                 | 【可选】文章分类                                                                                            | No       |
| keywords                   | 【可选】文章关键字                                                                                          | No       |
| description                | 【可选】文章描述                                                                                            | No       |
| top_img                    | 【可选】文章顶部图片                                                                                        | No       |
| cover                      | 【可选】文章缩略图（如果没有设置 top_img，文章页顶部将显示缩略图，可设为 false/图片地址/留空）              | No       |
| comments                   | 【可选】显示文章评论模块（默认 true）                                                                       | No       |
| toc                        | 【可选】显示文章 TOC（默认为设置中 toc 的 enable 配置）                                                     | No       |
| toc_number                 | 【可选】显示 toc_number（默认为设置中 toc 的 number 配置）                                                  | No       |
| toc_style_simple           | 【可选】显示 toc 简洁模式                                                                                   | No       |
| copyright                  | 【可选】显示文章版权模块（默认为设置中 post_copyright 的 enable 配置）                                      | No       |
| copyright_author           | 【可选】文章版权模块的文章作者                                                                              | No       |
| copyright_author_href      | 【可选】文章版权模块的文章作者链接                                                                          | No       |
| copyright_url              | 【可选】文章版权模块的文章连结链接                                                                          | No       |
| copyright_info             | 【可选】文章版权模块的版权声明文字                                                                          | No       |
| mathjax                    | 【可选】显示 mathjax（当设置 mathjax 的 per_page: false 时，才需要配置，默认 false）                        | No       |
| katex                      | 【可选】显示 katex（当设置 katex 的 per_page: false 时，才需要配置，默认 false）                            | No       |
| aplayer                    | 【可选】在需要的页面加载 aplayer 的 js 和 css                                                               | No       |
| highlight_shrink           | 【可选】配置代码框是否展开（true/false）（默认为设置中 highlight_shrink 的配置）                            | No       |
| aside                      | 【可选】显示侧边栏（默认 true）                                                                             | No       |
| abcjs                      | 【可选】加载 abcjs（当设置 abcjs 的 per_page: false 时，才需要配置，默认 false）                            | No       |
| noticeOutdate              | 【可选】文章过期提醒（默认为设置中 noticeOutdate 的 enable 配置）                                           | No       |

## Page Front-matter

| Parameter          | Explanation                                                                                                 | Required |
|--------------------|-------------------------------------------------------------------------------------------------------------|----------|
| title              | 【必需】页面标题                                                                                            | Yes      |
| date               | 【必需】页面创建日期                                                                                        | Yes      |
| type               | 【必需】标签、分类和友情链接三个页面需要配置                                                                | Yes      |
| updated            | 【可选】页面更新日期                                                                                        | No       |
| description        | 【可选】页面描述                                                                                            | No       |
| keywords           | 【可选】页面关键字                                                                                          | No       |
| comments           | 【可选】显示页面评论模块（默认 true）                                                                       | No       |
| top_img            | 【可选】页面顶部图片                                                                                        | No       |
| mathjax            | 【可选】显示 mathjax（当设置 mathjax 的 per_page: false 时，才需要配置，默认 false）                        | No       |
| katex              | 【可选】显示 katex（当设置 katex 的 per_page: false 时，才需要配置，默认 false）                            | No       |
| aside              | 【可选】显示侧边栏（默认 true）                                                                             | No       |
| aplayer            | 【可选】在需要的页面加载 aplayer 的 js 和 css                                                               | No       |
| highlight_shrink   | 【可选】配置代码框是否展开（true/false）（默认为设置中 highlight_shrink 的配置）                            | No       |
| random             | 【可选】配置友情链接是否随机排序（默认为 false）                                                            | No       |
| limit              | 【可选】配置说说显示数量                                                                                    | No       |
| limit.type         | 【可选】配置说说显示数量的类型（date 或者 num）                                                             | No       |
| limit.value        | 【可选】配置说说显示数量的值                                                                                | No       |