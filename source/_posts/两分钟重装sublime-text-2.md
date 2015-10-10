title: 两分钟重装sublime text 2
date: 2014-10-27 17:27:06
tags: [sublime]
categories: [front-end]
---
[sublime text](ttp://www.sublimetext.com) 虽好,却无奈会时不时会崩溃掉(频率 < 2次/年),而又只能手动安装、配置插件.故将符合本人使用习惯的版本还原方法在此备份如下:
###1.
打开 Sublime Text 2，按下** Control + `** 调出 Console，通常这个快捷键会与PC上的其它软件起冲突，需要修改其它软件的这个快捷键。

###2.
将以下代码粘贴进命令行中并回车：
    ```
    import urllib2,os;pf='Package Control.sublime-package';ipp=sublime.installed_packages_path();os.makedirs(ipp) if not os.path.exists(ipp) else None;open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())
    ```

###3.
重启 Sublime Text 2，如果在 `Preferences` -> `Package Settings`中见到`Package Control`这一项，就说明安装成功了。

###4.
`comond+shift+p` → `pci` → **Flatland **

###5.
`preference → setting-user` :
```
{
     "color_scheme": "Packages/Color Scheme - Default/Monokai Bright.tmTheme",
     "default_line_ending": "unix",
     "ensure_newline_at_eof_on_save": true,
     "font_face": "courier new",
     "font_size": 15.0,
     "highlight_line": true,
     "ignored_packages":
     [
          "Vintage",
          "jQuery Mobile Snippets"
     ],
     "scroll_past_end": false,
     "tab_size": 4,
     "theme": "Flatland Dark.sublime-theme",
     "trim_trailing_white_space_on_save": true,
     "word_wrap": true
}
```

###6.
`comond+shift+p` → `pci` :
emmet
ejs
less
juery
Prefixr
sublimeCodeIntel
Bracket Highlighter
markdown preview

###7.
拷贝备份的.sublime-snippet到 :
`/Users/userName/Library/Application Support/Sublime Text 2/Packages/User`
