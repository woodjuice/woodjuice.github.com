title: Hexo Notes
date: 2015-08-14 22:11:04
categories: Tech-Notes
tags: [Hexo, Technical note, Blog]
description: The tips of hexo.
---


### How to set muti-tags?

Try on this way when you need to set tags more than one.

```
tags: [Hexo, Technical note, Blog]
```

Then

![muti-tags](/img/tags.png)

<br></br>

### If I change to another computer, how to continue to use Hexo?

There are two computer: one named *old-pc*, another named *new-pc*.

1. Install [hexo-git-backup plugin](https://github.com/coneycode/hexo-git-backup) follow the instruction in *old-pc*. And backup your hexo files to github branch, such as *hexo-source-code*.

2. Change to *new-pc*, ```git clone``` your responsity, and switch to *hexo-source-code*.

3. Use ```npm install hexo``` to install hexo, and then ```hexo g```, ```hexo s```.

That's all!


<br></br>

### node-gyp rebuild?

When I try to install hexo on OS X 10.10.5, node-gyp rebuild cannot be installed correctly.

The solution is:  

> npm install hexo --no-optional  

Ref: https://github.com/hexojs/hexo/issues/1262  


<br></br>

    
 