---
layout: "home"
---
<script async src="https://cdnjs.cloudflare.com/ajax/libs/anchor-js/4.1.0/anchor.min.js" integrity="sha256-lZaRhKri35AyJSypXXs4o6OPFTbTmUoltBbDCbdzegg=" crossorigin="anonymous"></script>
<script>
document.addEventListener("DOMContentLoaded", function(event) {
  anchors.add(".dict h2");
});
</script>
<a href="https://github.com/dciccale/css3-github-ribbon" class="github-ribbon">
  Fork me on GitHub
</a>
<style>
    .dict-title {
        padding-bottom: 0.3em;
        font-size: 1.5em;
        border-bottom: 1px solid #eaecef;
    }
</style>
<div class="body">
{% if site.github %}
<a href="{{site.github.repository_url}}"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_right_darkblue_121621.png" alt="Fork me on GitHub"></a>
{% endif %}
{% for dict_hash in site.data.dict %}
{% assign dict = dict_hash[1] %}
  <div class="dict">
        {% if dict.id %}
        <h2 id="{{ dict.id }}" class="dict-title">{{dict.expected}}</h2>
        {% else %}
        <h2>{{dict.expected}}</h2>
        {% endif %}
        <p class="dict-item-tags">Tags:
            {% for tag in dict.tags %}
            <span class="dict-item-tag"><code>{{ tag }}</code></span>
            {% endfor %}
        </p>
        {% if dict.description != empty %}
        <h3>Description</h3>
        <p>{{dict.description}}</p>
        {% endif %}
        <h3>Patterns</h3>
        <table class="dict-item-pattens">
            <tr>
                <th>
                    Pattern
                </th>
                <th>
                    Expected
                </th>
            </tr>
            {% for pattern in dict.patterns %}
            <tr>
                <td>{{pattern}}</td>
                <td>{{dict.expected}}</td>
            </tr>
            {% endfor %}
        </table>
        {% if dict.specs.size > 0 %}
        <h3>Examples</h3>
        <table class="dict-item-specs">
            <tr>
                <th>
                    Before
                </th>
                <th>
                    After
                </th>
            </tr>
            {% for spec in dict.specs %}
            <tr>
                <td>{{spec.from}}</td>
                <td>{{spec.to}}</td>
            </tr>
            {% endfor %}
        </table>
        {% endif %}
    </div>
{% endfor %}
</div>
