---
layout: post
title: Make a blog with Jekyll and Github Pages
---

There are 3 ways to do this:
1. Install Jekyll locally via the command line, create a new boilerplate website using `jekyll new`, build it locally with `jekyll build`, and then serve it with `jekyll serve`.
2. Clone a starting point to your local machine, install Jekyll locally via the command line, make updates to your website, build it locally, and then serve it.
3. Fork a starting point, make changes, and then serve it.

I'm going to show the steps for 3 because it is the fastest and easiest.

## Pick a starting point
1. Browse the themes at [jekyllthemes.org](http://jekyllthemes.org). When you find one you like, find its Github repo by clicking "Homepage". I picked the [Jekyll Now](https://github.com/barryclark/jekyll-now) theme and some of the optional steps will be tailored to it. Hopefully it's straightforward enough to be adapted to other themes.
2. On the Github repo, click fork in the top right.
3. Visit the repository in your account, click settings, and rename the repository `yourusername.github.io`.
4. Your site should be up and running at `https://yourusername.github.io`

## Making changes to the site
You can edit files for your blog in two ways:
1. Edit files in your new username.github.io repository directly in the browser.
2. Clone your repository and make changes locally, then push them to your GitHub repository

You can change many of the properties of the site by editing the `_config.yml` file.

## Publishing your first blog post
Edit `/_posts/2014-3-3-Hello-World.md`. You can edit/delete everything, just include the front matter at the top.


## Optional steps

### Use your own domain
1. Edit the `CNAME` file to include your domain name e.g. `www.yourdomainname.com`
2. Visit your domain registrar and add a CNAME DNS record pointing your domain to Github pages.
    - type: `CNAME`
    - host: `www.yourdomainname.com`
    - answer: `yourusername.github.io`
    - TTL: `300`


### Customizing your theme
If you want to make substantial changes, building and testing your site locally may be more convenient. You'll need to have Ruby and Jekyll installed. Easiest way to do that on Mac is
```bash
brew install ruby
gem install github-pages
```
The workflow for building and viewing your site locally:
1. `cd yourusername.github.io`
2. `jekyll serve --watch` serve the site, rebuilding on any changes
3. visit 127.0.0.1:4000/ in browser
4. When done, commit changes and push to master branch.


### Set up comments
Most blogs use Disqus. Some themes support it by default and it's as easy as adding your account in `_config.yml`. I'm not a big fan of Disqus and use [utteranc.es](https://utteranc.es) instead. It uses Github issues to store comment threads. I created a new file `_includes/utterances.html` with the code below and imported it into `_layouts/post.html` by appending `{ % include utterances.html %}`.
```html
<script src="https://utteranc.es/client.js"
    repo="username/username.github.io"
    issue-term="pathname"
    theme="github-light"
    crossorigin="anonymous"
    async>
</s>
```

### Set up MathJax
[MathJax](https://www.mathjax.org) is a JavaScript display engine for mathematics. I created a new file `_includes/mathjax.html` with the code below and imported it into `_layouts/post.html` by appending `{ % include mathjax.html %}`.
```html
<script type="text/x-mathjax-config">
MathJax.Hub.Config({
    tex2jax: {
    skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
    inlineMath: [['$','$']]
    }
});
</script>
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script> 
```

Here's what it looks like:

**Theorem**: There exist two irrational numbers $x$, $y$ such that $x^y$ is rational.

*Proof.* If $x=y=\sqrt2$ is an example, then we are done; otherwise $\sqrt2^{\sqrt2}$ is irrational, in which case taking $x=\sqrt2^{\sqrt2}$ and $y=\sqrt2$ gives us:
$$\left(\sqrt2^{\sqrt2}\right)^{\sqrt2}=\sqrt2^{\sqrt2\sqrt2}=\sqrt2^2=2.\qquad\square$$


## Conclusion
I tried to write this tutorial very concisely. Let me know if the format worked or if it was too brief.