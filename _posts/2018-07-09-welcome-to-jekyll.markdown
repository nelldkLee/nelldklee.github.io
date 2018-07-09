---
layout: post
title:  "Welcome to Jekyll!"
date:   2018-07-09 12:00:49 +0900
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight java %}
package org.generals.controller;

import java.security.Principal;

import org.generals.domain.Criteria;
import org.springframework.context.annotation.Scope;
import org.springframework.context.annotation.ScopedProxyMode;
import org.springframework.security.access.prepost.PreAuthorize;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
import org.springframework.web.bind.annotation.PostMapping;
import org.springframework.web.servlet.mvc.support.RedirectAttributes;

@PreAuthorize("isAuthenticated()")
public interface GenericController<T, K> {

	@GetMapping("/list")
	@PreAuthorize("permitAll")
	public void list(Criteria cri, Model model, Principal principal) throws Exception;

	@GetMapping("/view")
	public void view(K key, Criteria cri, Model model) throws Exception;

	@GetMapping("/register")
	public void register(Criteria cri) throws Exception;

	@PostMapping("/register")
	public String registerPost(T vo, Criteria cri, RedirectAttributes rttr);

	@GetMapping("/modify")
	public void modify(K key, Criteria cri, Model model) throws Exception;

	@PostMapping("/modify")
	public String modifyPost(T vo, Criteria cri, RedirectAttributes rttr) throws Exception;

	@PostMapping("/remove")
	public String removePost(K key, Criteria cri, Model model, RedirectAttributes rttr) throws Exception;

}
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
