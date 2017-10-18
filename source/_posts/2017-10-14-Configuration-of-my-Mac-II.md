---
title: Configuration of my Mac II
date: 2017-10-14 14:06:38
tags:
- Mac
- Application
---

After one year and a half, apps don't catch my attention any more, since they're complete whole which is easy to get back. Trifles, like connection to github and theme of sublime text, are much more important.

Due to some disappointment, I've restored my mac again. However, this time my portal disk was lost, and I have to configure a brand new system!

That's really annoying, so that I write the process down.

<!--more-->

# Applications

Generally speaking, apps are not difficult to configure. I only have to set them according to my custom. **BUT**, I've just about forgot the name of my sublime text's theme. And the new version(3143) support for custom color window title bars, which is what I've been expecting for so long. Therefore, I'll record how to configure it.

<img src="http://tc.ffsky.net/images/2017/10/14/64ce612629437628c3987116ba3851fb.png" alt="64ce612629437628c3987116ba3851fb.png" border="0">

The 'color_theme' is "MonokaiGray".

the 'theme' is 'Spacegray Eighties', But I remember that it used to be 'MonokaiGray' as well which cannot be found anymore.

Then, the theme dosen't contain the title part. You should add this code at the beginning.

```
// Title
{
	"class": "title_bar",
    "fg": ["background", 255, 255, 255, 0.7],
    "bg": ["background", 0, 0, 0, 0]
},
```

To change the config, you're ought to install *PackageResourceViewer* by *Package Control* which is bond to ST3 now.

Other plug-ins:

- *BracketHighlighter*
- *Ctags*
- *ConverToUTF8*

# Blog

I think that I've upload my config, but the **FACT** is that I uploaded part of them.

So I build my blog from square one, and I submit a complete backup this time. Now that I have a backup, how to rebuild it from the backup is important.

## Prepare for hexo

hexo need Node.js and Git,  and I need to install the former.

write this code to get nvm which is the best tool to install Node.js:

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.5/install.sh | bash
```

And you should have a file name '.bash_profile' at your user's root before.

Then you should install Node.js 6.11.4.

## Get the Files from github

At first you should generate a RSA key, and upload it to your github account.

then:

```
git clone git@github.com:YOUR_REPO.git
```

**ATTETION**: Don't use "https://..." but "git@github.com…": which use ssh, otherwise you need to input your id and password everytime.

## Install hexo

First change your directory to your blog, then:

```
npm install hexo --save
npm install
npm install hexo-deployer-git --save
```

That's all, your blog is ready now.

# Others

差点忘了，我习惯隐藏dock与menubar。它们的弹出有一定的延迟，习惯无延迟后再突然加上延迟可是相当令人恼火的。

```
defaults write com.apple.Dock autohide-delay -int 0 && killall Dock 
```

在终端输入以上代码后即可零延迟弹出Dock