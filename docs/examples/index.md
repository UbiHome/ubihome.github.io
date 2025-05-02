# Examples

Here you can find some examples for using UbiHome.
Parts of it are just shared configuration files you could reuse for you purposes - others are full blown guides.

<ul>
  {% for nav1 in navigation %}
    {% if nav1.title == 'Examples' %}
    {% if nav1.children and nav1.children | length > 1 %}
    <ul>
        {% for nav2 in nav1.children %}
            {% if nav2.url %}
            {% if nav2.title %}
            <!-- <li><a href="/{{ nav2.url }}">{{ nav2.title }} </a></li> -->
            {% endif %}
            {% else %}
            <li><a href="{{ config.site_url }}{{ nav2.children[0].url }}">{{ nav2.title }} </a></li>
            {% endif %}

            {% if nav2.children and nav2.children | length > 1 %}
            <ul>
            {% for nav3 in nav2.children %}
                {% if nav3.url %}
                {% if nav3.title %}
                <li><a href="{{ config.site_url }}{{ nav3.url }}">{{ nav3.title }} </a></li>
                {% endif %}
                {% else %}
                {% endif %}
            {% endfor %}
            </ul>
            {% endif %}
        {% endfor %}
        </ul>
    {% endif %}
    {% endif %}
  {% endfor %}
</ul>