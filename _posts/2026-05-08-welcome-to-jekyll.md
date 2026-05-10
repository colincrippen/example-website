---
layout: post
title:  "Welcome to Jekyll!"
date:   2026-05-08 15:20:55 -0500
categories: jekyll update
---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

Jekyll requires blog post files to be named according to the following format:

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight c linenos %}
#include <stdio.h>

#define ARR_LEN 7

void qsort(int v[], int left, int right);
void printArr(int v[], int len);

int main() {
    int i;
    int v[ARR_LEN] = { 4, 3, 1, 7, 9, 6, 2 };
    printArr(v, ARR_LEN);
    qsort(v, 0, ARR_LEN - 1);
    printArr(v, ARR_LEN);
    return 0;
}

void qsort(int v[], int left, int right) {
    int i, last;
    void swap(int v[], int i, int j);

    if (left >= right)
        return;
    swap(v, left, (left + right) / 2);
    last = left;
    for (i = left + 1; i <= right; i++)
        if (v[i] < v[left])
            swap(v, ++last, i);
    swap(v, left, last);
    qsort(v, left, last - 1);
    qsort(v, last + 1, right);
}

void swap(int v[], int i, int j) {
    int temp;

    temp = v[i];
    v[i] = v[j];
    v[j] = temp;
}

void printArr(int v[], int len) {
    int i;
    for (i = 0; i < len; i++)
        printf("%d ", v[i]);
    printf("\n");
}
{% endhighlight %}
*Code snippet from [here][source-link]*

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

[source-link]: https://github.com/Heatwave/The-C-Programming-Language-2nd-Edition/blob/master/chapter-4-functions-and-program-structure/8.qsort.c