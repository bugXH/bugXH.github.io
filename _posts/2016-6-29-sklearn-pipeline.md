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

When making predictions, the method predict() is used. As suggested by the documentation of sklearn, the method "Applies transforms to the data, and the predict method of the final estimator."

So the transformation uses the same features (vocabularies) learned from the training docs

