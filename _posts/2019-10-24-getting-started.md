---
layout: post
title: Getting Started with Blogging
---

I wanted to start a blog. I chose to use [Jekyll](https://github.com/jekyll/jekyll) and Github pages over Medium or another service because I wanted to feel in control of my content and how it's presented. Some features I wanted included code blocks with syntax highlighting, Latex rendering, and comments.


## Getting Started
I started by cloning the [Jekyll Now](https://github.com/barryclark/jekyll-now) repository, a simple theme I liked. I removed the stuff I didn't need and tweaked the css for code blocks.


## Comments
A popular comment solution I see on blogs is Disqus. In line with the desire to own my content, I decided to use [utteranc.es](https://utteranc.es) instead. It uses Github issues to store comment threads.

I created a new file `utterances.html` with the code below and imported it into `post.html`.
```html
<script src="https://utteranc.es/client.js"
    repo="benburk/benburk.github.io"
    issue-term="pathname"
    theme="github-light"
    crossorigin="anonymous"
    async>
</s>
```

## Analytics
Google Analytics was easy to set up. I simply made an account and added the Google Analytics web tracking code to the appropriate field in `_config.yml`.


## Math
[MathJax](https://www.mathjax.org) is a JavaScript display engine for mathematics. I created a new file `mathjax.html` with the code below and imported it into `post.html`.
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

Testing it out with a neat proof:

**Theorem**: There exist two irrational numbers $x$, $y$ such that $x^y$ is rational.

*Proof.* If $x=y=\sqrt2$ is an example, then we are done; otherwise $\sqrt2^{\sqrt2}$ is irrational, in which case taking $x=\sqrt2^{\sqrt2}$ and $y=\sqrt2$ gives us:
$$\left(\sqrt2^{\sqrt2}\right)^{\sqrt2}=\sqrt2^{\sqrt2\sqrt2}=\sqrt2^2=2.\qquad\square$$


## Syntax Highlighting
I didn't like how the default code blocks looked, so I modified them by changing the `.highlight` block in `_highlights.scss` to
```css
.highlight {
  background-color: #efefef;
  margin: 5px 5px 5px 5px;
  overflow: scroll;
}
```
Now they look like this:

```python
def shuffle(arr):
    """Shuffle an array"""
    for i, elem in enumerate(arr):
        rand_idx = random.randrange(i, len(arr))
        arr[i], arr[rand_idx] = arr[rand_idx], elem
    return arr
```