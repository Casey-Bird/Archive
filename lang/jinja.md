## Jinja is automatically parsed when using Flask

Simple variable
```html
<h1>Hello {{ user_name }}</h1>
```

## Filters

Filters are basically functions that can be used on variables while inside of html code. Google "jinja2 filters" to see them all.
```html
<h1>Hello {{ user_name|upper }}</h1>
```

# Logic Inside of HTML using Jinja

These are logic blocks that show how to perform functions while still coding in html, allows for backend communication.
```html
{% for topping in favorite_pizza %}
      put html code here
{% endfor %}

{{ favorite_pizza.0 }} # This get's the 0 item in a list named favorite_pizza
.0 is the same as [0]

{% if topping == "pepperoni" %}
  {{ topping = "It was pepperoni" }}
{% elseif topping == "sausage" %}
  {{ topping = "It wasn't pepperoni" }}
{% else %}
  {{ topping = "Else stuff"}}
{% endif %} # TODO MAKE SURE TO END EVERY BIT OF CODE LOGIC
```