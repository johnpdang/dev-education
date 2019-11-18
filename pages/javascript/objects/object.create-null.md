# Object.create\(null\)

{% code title="Create empty object" %}
```text
Object.create(null)
```
{% endcode %}

The easiest way to set it up as **totally empty** is `Object.create(null)`is similar to `{ }`, but without the delegation to `Object.prototype`, so it's "more empty" than just `{ }`.

