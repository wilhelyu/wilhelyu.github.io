---
title: GitHub Pages + Jekyll + Vercel 搭建个人博客
categories: [note]
---

## 本地环境

1. 安装 Ruby 和 Ruby Gems <https://jekyllrb.com/docs/installation/>
   - Windows `winget install RubyInstallerTeam.RubyWithDevKit.3.2 -l "D:\Winget\Ruby"`
2. 安装 Jekyll `gem install jekyll bundler`
3. 检查是否安装成功 `ruby -v`  `jekyll -v`
4. Clone [模版](https://github.com/huangyz0918/moving)至本地 `git clone git@github.com:huangyz0918/moving.git`
5. 进入项目文件夹，安装所需 gems `bundle install`  `bundle add webrick`
   - 默认安装的 bundle 版本为 2.4.22，报错版本不适配

    ```powershell
    Because the current Bundler version (2.4.22) does not satisfy bundler ~> 2.3.26 and Gemfile depends on bundler ~> 2.3.26, version solving has failed.
    Your bundle requires a different version of Bundler than the one you're running.
    Install the necessary version with `gem install bundler:2.3.27` and rerun bundler using `bundle _2.3.27_ install`
    ```

6. 运行 Jekyll `bundle exec jekyll serve`
7. 访问 <http://localhost:4000>

## 部署流程

### 部署至 GitHub Pages

创建仓库，命名为 `{username}.github.io`

进入 Pages 设置，Source 选择 GitHub Action，会自动生成 GitHub Action 文件

等待触发第一次 Workflow，完成后即可访问网页

![ ](/assets/img/GitHubPages.png)

### 部署至 Vercel

![ ](/assets/img/Vercel.png)

## 博客优化

### 不蒜子

<https://busuanzi.ibruce.info/>

极简网页计数器，两行代码搞定 PV、UV 统计。

```html
<script async src="https://busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
<span class="busuanzi_container_page">
 <span id="busuanzi_container_page_pv">
  •
  <span id="busuanzi_value_page_pv"></span> View
 </span>
</span>
```

### giscus

<https://giscus.app/zh-CN>

由 GitHub Discussion 驱动的评论系统。
