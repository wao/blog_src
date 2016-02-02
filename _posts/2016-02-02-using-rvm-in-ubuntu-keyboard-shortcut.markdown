---
layout: post
title: Using rvm script in ubuntu keyboard shortcuts
tags: ubuntu ruby rvm
---

Recently, I try to using ubuntu keyboard shortcuts to launch my ruby scripts.

Surprisingly, I found the script seemed hadn't been excuted at all. After some research, I realize that the root cause is that I write ruby and run it with rvm.

To use rvm, some code line needed to be added into `.bashrc` or `.bash_profile`. However, scripts launched by keybord shortcuts or `ALT+F2` knows nothing about rvm. So your ruby script commonly failed due to require gem failures. For example, you use gem `main` and using `gem install main` in console. This gem is installed in rvm managered gem path. However, ruby launched by keyboard shortcuts only run system ruby and don't have gem `main` installed. To fix this problem, I found that `rvm wrapper` can rescure us. I used following command `rvm wrapper 2.2.1@defrvm defrv`. This command will create a `defrvm_ruby` script. Then in keybord shutcuts using `path/to/defrvm_ruby path/to/your_script` instead of `path/to/your_script`. Then script can correctly find its dependencies.
