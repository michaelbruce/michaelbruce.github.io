---
layout: default
title: Using onclick in clojurescript
---

# Using onclick in clojurescript

As part of my efforts to learn clojure, I have been writing a web application in clojurescript for tracking money and time called balance *make link*

What I want to do is add a css class to an element.

....there are multiple hide buttons lala should hide the related table/element

{% highlight clojure %}
(defn hide-table [name]
  (do
    (println (str "hide-table method call for: " name))))
{% endhighlight %}

I start off writing the method that will contain the logic that will hide tables when I click the hide button. For now I will include a print statement to the console so I know the onclick is working.

I would have liked to do this via a REPL, I am quite sure there is a way to do this but I am not currently aware of how to do so, currently using figwheel and the feedback is adequate for this purpose.

I have added #test to all my tables (since they are created by the same function, this change happens in one place)

{% highlight clojure %}
(defn hide-table [name]
  (do
    (println (str "hide-table method call for: " name))
    (println (.classList.add (.getElementById js/document "test") "hidden"))))
{% endhighlight %}

This will now hide the first table on the page. I am not familiar with javascript and can't tell why only the first element was chosen.

I want to be able to toggle the hidden class on and off. I'd also like the hide button to apply to the nearest table only.

A lot of trouble I have is getting objects but being unable to print them out, errors are returned in the console like this. (image time!)

{% highlight clojure %}
(println (str (keys (.getElementById js/document "test"))))
{% endhighlight %}

I thought I'd be able to cheat a little here by using an inbuilt javascript class toggling function.
This did not work and returned a yellow warning.

{% highlight clojure %}
(.classList.toggle (.getElementById js/document "test") "hidden" "data-table")
{% endhighlight %}

This does detect if an element contains a certain class

{% highlight clojure %}
(println (.classList.contains (.getElementById js/document "test") "hidden"))
{% endhighlight %}

{% highlight clojure %}
(defn hide-table [name]
  (do
    (println (str "hide-table method call for: " name))
    (if (.classList.contains (.getElementById js/document "test") "hidden")
      (.classList.remove (.getElementById js/document "test") "hidden")
      (.classList.add (.getElementById js/document "test") "hidden"))))
{% endhighlight %}

This does what I want but it's hella messy.

Pretty sure there is a reagent way of doing things - a way to make changes by isolated state so I should read up more on that.


