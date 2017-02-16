---
layout: default
title: Barebones Boot Tutorial
---

# Barebones Boot Tutorial

Here's a short description of how to hit the ground running with the Clojure(script) build tool boot!

- Install boot using this command `sudo bash -c "cd /usr/local/bin && curl -fsSLo boot https://github.com/boot-clj/boot-bin/releases/download/latest/boot.sh && chmod 755 boot"`

- Create a build.boot file in a new directory `mkdir new-project && touch new-project/build.boot`, it should contain the following:

{% highlight clojure %}
(set-env!
 :source #{"src"}
 :dependencies '[[org.clojure/clojure "1.8.0"]])
{% endhighlight %}

*At this point you should be able to run `boot repl` and you're basically good to go*

- From here you can include additional dependencies and create new tasks to run from the command line e.g `boot build` with the deftask macro like so:

{% highlight clojure %}
(set-env!
 :source #{"src"}
 :dependencies '[[org.clojure/clojure "1.8.0"]
                 [that.sweet/new-dependency "0.0.1"]])

(deftask build
  "Build uberjar"
  []
  (comp (aot) (pom) (uber)
        (jar :file "watermarker.jar")
        (sift :include #{#"watermarker.jar"})
        (target "target")))
{% endhighlight %}
