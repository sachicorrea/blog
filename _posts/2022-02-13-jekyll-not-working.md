---
layout: post
title: Bad interpreter - no file or folder in Jekyll
tags: jekyll
date: 2022-02-13 22:22 -0500
---

Hi everyone. A few days ago, I was trying to run this blog locally, but I got an error that drove me crazy for a few minutes.

**bad interpreter: no file or folder**

I have to admit that I abandoned this blog for many months, and during this period of inactivation I updated my OS version, moving from Ubuntu 18.04 to 20.04, so when I tried to run the Jekyll server again, everything turned into a complete mess.

Immediately, I searched for this error and found an answer on the [askubuntu.com][1]{:target="\_blank"} website that works perfectly for me, especially answers made by users Piotr and juneja, which I prefer to summarize here. First of all, open a new terminal and run the following commands to uninstall and re-install Jekyll. In this case, you don't need to go to the folder where the Jekyll project is located because Jekyll as well as Bundler gems were installed globally.

```
gem uninstall jekyll
gem install jekyll
```

After that, run the following commands in order to uninstall and re-install the bundler gem into the home folder in the terminal.

```
gem uninstall bundler
gem install bundler
```

The final step is to update the _config.yml file located in the root of your Jekyll project, looking for the row where the jekyll gem is required and changing its version for the current one installed. In my case:

`gem "jekyll", "~> 4.2.1"`

Completed the steps described above, run `bundle exec jekyll serve` in your Jekyll project's folder and you will interact with it in your developer environment again.


*Citations: [Jekyll broken after upgrading Ubuntu/Ruby][2]{:target="\_blank"}*

[1]: https://askubuntu.com/
[2]: https://askubuntu.com/questions/785196/jekyll-broken-after-upgrading-ubuntu-ruby