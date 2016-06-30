---
layout: post
title: sklearn pipeline features
---
An example of using pipeline:

{% highlight python %}
senti_clf = Pipeline([
                      ('vect', CountVectorizer()),
                      ('tfidf', TfidfTransformer()),
                      ('clf', LinearSVC()),
                      ])
{% endhighlight %}


The input is raw documents. The pipeline first learned the vocabularies (features), then transform into feature matrix, finally fit the classifier for training

When making predictions, the method predict() is used. As stated by the [documentation of sklearn pipeline](http://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html), the method

**"Applies transforms to the data, and the predict method of the final estimator."**

So the transformation uses the same features (vocabularies) learned from the training docs

