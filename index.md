---
layout: "home"
---
<script async src="https://cdnjs.cloudflare.com/ajax/libs/anchor-js/4.1.0/anchor.min.js" integrity="sha256-lZaRhKri35AyJSypXXs4o6OPFTbTmUoltBbDCbdzegg=" crossorigin="anonymous"></script>
<script>
document.addEventListener("DOMContentLoaded", function(event) {
  anchors.add(".proofdict-title");
});
</script>
<style>
    .proofdict-title {
        padding-bottom: 0.3em;
        font-size: 1.5em;
        border-bottom: 1px solid #eaecef;
    }
</style>
<div class="body">
{% if site.github %}
<a href="{{site.github.repository_url}}"><img style="position: absolute; top: 0; right: 0; border: 0;" src="https://s3.amazonaws.com/github/ribbons/forkme_right_darkblue_121621.png" alt="Fork me on GitHub"></a>
{% endif %}
{% for proofdict_hash in site.data.proofdict %}
{% assign proofdict = proofdict_hash[1] %}
  <div class="proofdict">
        {% if proofdict.id %}
        <h2 id="{{ proofdict.id }}" class="proofdict-title">{{proofdict.expected}}</h2>
        {% else %}
        <h2 class="proofdict-title">{{proofdict.expected}}</h2>
        {% endif %}
        <p class="proofdict-item-tags">Tags:
            {% for tag in proofdict.tags %}
            <span class="proofdict-item-tag"><code>{{ tag }}</code></span>
            {% endfor %}
        </p>
        {% if proofdict.description != empty %}
        <div class="proofdict-description">
            <h3>Description</h3>
            <p class="proofdict-descriptionBody">{{proofdict.description}}</p>
        </div>
        {% endif %}
        <div class="proofdict-patterns">
            <h3>Patterns</h3>
            <table class="proofdict-pattens-table">
                <tr>
                    <th>
                        Pattern
                    </th>
                    <th>
                        Expected
                    </th>
                </tr>
                {% for pattern in proofdict.patterns %}
                <tr>
                    <td>{{pattern}}</td>
                    <td>{{proofdict.expected}}</td>
                </tr>
                {% endfor %}
            </table>
        </div>
        {% if proofdict.specs.size > 0 %}
        <div class="proofdict-examples">
        <h3>Examples</h3>
            <table class="proofdict-examples-table">
                <tr>
                    <th>
                        Before
                    </th>
                    <th>
                        After
                    </th>
                </tr>
                {% for spec in proofdict.specs %}
                <tr>
                    <td>{{spec.from}}</td>
                    <td>{{spec.to}}</td>
                </tr>
                {% endfor %}
            </table>
        </div>
        {% endif %}
    </div>
{% endfor %}
</div>
