---
layout: default
permalink: /work/
---

<div class="week hrow">
    <div class="week_id">Week</div>
    <div class="date">Deadline (10:00pm)</div>
    <div class="lab">Labs</div>
    <div class="hw">Assignments</div>
    <div class="project">Project</div>
</div>

{% assign week_id = 0 %}
{% for e in site.data.work %}
<div class="week {% cycle "odd", "even" %}">
    {% if e.break %}
        <div class="week_id"></div>
    {% else %}
        {% assign week_id = week_id | plus: 1 %}
        <div class="week_id">{{ week_id }}</div>
    {% endif %}
    <div class="date"></div>
    <div class="lab">
        {% if e.lab %}
             {% if e.lab.handout %}
                 <a href="{{e.lab.handout}}">{{e.lab.title}}</a>
             {% else %}
                 {{e.lab.title}}
              {% endif %}
              {% if e.lab.rubric %}
                  <a href="{{e.lab.rubric}}">(rubric)</a>
               {% endif %}
        {% endif %}
    </div>
    <div class="hw">
        {% if e.hw %}
            {% if e.hw.handout %}
                <a href="{{e.hw.handout}}">{{e.hw.title}}</a>
            {% else %}
                {{e.hw.title}}
             {% endif %}
             {% if e.hw.rubric %}
                 <a href="{{e.hw.rubric}}">(rubric)</a>
              {% endif %}
         {% endif %}
    </div>
    <div class="project">
        {% if e.project %}
            {% if e.project.handout %}
                <a href="{{e.project.handout}}">{{e.project.title}}</a>
            {% else %}
                {{e.project.title}}
             {% endif %}
         {% endif %}
    </div>
</div>
{% endfor %}

**All project deliverables are due Friday April 8, 10pm (strict deadline)**

<script type="text/javascript">
   make_schedule({{site.data.settings.first}},7,6);
</script>
   

