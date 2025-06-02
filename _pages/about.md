---
layout: default
title: STAR Group
permalink: /
---

<h1 style="display: flex; align-items: center; gap: 0.5em;">
  <img src="/assets/img/STAR.png" alt="STAR Logo" style="height: 1.5em;">
  <span>
    <strong>STAR</strong>: 
    <span class="text-primary">S</span>pace&#8209;<span class="text-primary">T</span>ime 
    C<span class="text-primary">a</span>usality 
    <span class="text-primary">R</span>eading Group
  </span>
</h1>


Welcome to the STAR Group, a reading group dedicated to exploring **causal inference in spatio-temporal systems**, including methodological, theoretical, and applied perspectives. We meet **every other Wednesday at 15:00 CET** on Microsoft Teams.

<div style="margin-top: 2em;"></div>
---
## 🗓️ Schedule
---
<div style="margin-top: 2em;"></div>

{% assign today = 'now' | date: "%Y-%m-%d" %}
{% assign upcoming_sessions = "" | split: "" %}

{% for session in site.data.schedule %}
  {% assign session_date = session.date | date: "%Y-%m-%d" %}
  {% if session_date >= today %}
    {% assign upcoming_sessions = upcoming_sessions | push: session %}
  {% endif %}
{% endfor %}

{% assign sorted_sessions = upcoming_sessions | sort: "date" %}

{% if sorted_sessions.size > 0 %}
  {% assign next_session = sorted_sessions.first %}
  <div class="next-session">
  <h3>Next Session</h3>
  <p><strong>Date:</strong> {{ next_session.date }}</p>
  <p><strong>Topic:</strong> {{ next_session.topic }}</p>
  <p><strong>Speaker:</strong> {{ next_session.speaker }}</p>
  <p><strong>Resources:</strong>
  {% if next_session.paper or next_session.slides %}
    {% assign resources = "" %}
    {% if next_session.paper %}
      {% assign resources = resources | append: '<a href="' | append: next_session.paper | append: '">Paper</a>' %}
    {% endif %}
    {% if next_session.slides %}
      {% if resources != "" %}
        {% assign resources = resources | append: ', ' %}
      {% endif %}
      {% assign resources = resources | append: '<a href="' | append: next_session.slides | append: '">Slides</a>' %}
    {% endif %}
    {{ resources | raw }}
  {% else %}
    <a href="mailto:spacetimecausality@gmail.com?subject=Resource%20Request%20for%20{{ next_session.topic | uri_escape }}">Request Resources</a>
  {% endif %}
</p>
  </div>
{% else %}
  <div class="no-session">
    <h3>No Upcoming Sessions</h3>
    <p>
      We currently have no scheduled sessions. Want to speak at a future session? Please drop us an email.
    </p>
  </div>
{% endif %}

---
<div style="margin-top: 2em;"></div>
### 🔙 Previous Sessions

<p>All past sessions are listed below. Slides and recordings are available upon request if not directly linked.</p>

{% assign today = 'now' | date: "%Y-%m-%d" %}
{% assign past_sessions = "" | split: "" %}

{% for session in site.data.schedule %}
  {% assign session_date = session.date | date: "%Y-%m-%d" %}
  {% if session_date < today %}
    {% assign past_sessions = past_sessions | push: session %}
  {% endif %}
{% endfor %}

{% assign sorted_sessions = past_sessions | sort: "date" | reverse %}

<div style="overflow-x:auto; margin-top: 2em;">
  <table style="width: 100%; border-collapse: collapse;">
    <thead>
      <tr>
        <th style="text-align: left; padding: 8px; white-space: nowrap;">Date</th>
        <th style="text-align: left; padding: 8px;">Topic</th>
        <th style="text-align: left; padding: 8px;">Resources</th>
        <th style="text-align: left; padding: 8px;">Speaker</th>
      </tr>
    </thead>
    <tbody>
      {% for session in sorted_sessions %}
        <tr>
          <td style="padding: 8px; white-space: nowrap;">{{ session.date }}</td>
          <td style="padding: 8px;">{{ session.topic }}</td>
          <td style="padding: 8px;">
            {% assign resources = "" %}
            {% if session.paper %}
              {% assign resources = resources | append: '<a href="' | append: session.paper | append: '">Paper</a>' %}
            {% endif %}
            {% if session.slides %}
              {% if resources != "" %}
                {% assign resources = resources | append: ', ' %}
              {% endif %}
              {% assign resources = resources | append: '<a href="' | append: session.slides | append: '">Slides</a>' %}
            {% endif %}
            {% if resources != "" %}
              {{ resources | raw }}
            {% else %}
              <a href="mailto:spacetimecausality@gmail.com?subject=Resource%20Request%20for%20{{ session.topic | uri_escape }}">Request</a>
            {% endif %}
          </td>
          <td style="padding: 8px;">{{ session.speaker }}</td>
        </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

<!-- ### Upcoming Planned Sessions


{% assign today = 'now' | date: "%Y-%m-%d" %}
{% assign future_sessions = "" | split: "" %}

{% for session in site.data.schedule %}
  {% assign session_date = session.date | date: "%Y-%m-%d" %}
  {% if session_date >= today %}
    {% assign future_sessions = future_sessions | push: session %}
  {% endif %}
{% endfor %}
---
{% assign sorted_future_sessions = future_sessions | sort: "date" %}

{% if sorted_future_sessions.size > 0 %}
  <div style="overflow-x:auto;">
  <table style="width: 100%; border-collapse: collapse;">
    <thead>
      <tr>
        <th style="text-align: left; padding: 8px; white-space: nowrap;">Date</th>
        <th style="text-align: left; padding: 8px;">Topic</th>
        <th style="text-align: left; padding: 8px;">Paper</th>
        <th style="text-align: left; padding: 8px;">Speaker</th>
      </tr>
    </thead>
    <tbody>
      {% for session in sorted_future_sessions %}
      <tr>
        <td style="padding: 8px; white-space: nowrap;">{{ session.date }}</td>
        <td style="padding: 8px;">{{ session.topic }}</td>
        <td style="padding: 8px;">
          {% if session.paper %}
            <a href="{{ session.paper }}">Paper</a>
          {% else %}
            N/A
          {% endif %}
        </td>
        <td style="padding: 8px;">{{ session.speaker }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
  </div>
{% else %}
  <p><em>No upcoming sessions planned yet.</em></p>
{% endif %} -->
 --- 
<div style="margin-top: 2em;"></div>

## 🙌 How to Participate

We welcome anyone interested in causal methods and spatio-temporal modeling to join the **STAR** Group!

### Session Format

Each session features a short (~20–30 min) presentation followed by an open discussion.  
We ask that participants read or skim the paper in advance so we can focus on meaningful questions and ideas.

### Joining the Group

To join, just email us at <span id="email-link">email us</span> with your name, affiliation, and a few words about your interest.<br>
We look forward to welcoming new faces ; we do ask for regular participation and active engagement.

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const user = "spacetimecausality";
    const domain = "gmail.com";
    const email = `${user}@${domain}`;
    const strong = document.createElement("strong");
    strong.textContent = email;
    document.getElementById("email-link").replaceWith(strong);
  });
</script>


**Want to present a paper or lead a session?** Let us know!

----
<div style="margin-top: 2em;"></div>
## 👥 Organizers

<style>
  .organizers {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5em;
    margin-top: 1em;
  }

  .organizer {
    text-align: center;
    width: 120px;
  }

  .organizer img {
    width: 100px;
    height: 100px;
    object-fit: cover;
    border-radius: 50%;
  }

  .organizer p {
    margin-top: 0.5em;
    font-size: 0.95em;
  }
</style>

<div class="organizers">
  <div class="organizer">
    <a href="https://www.linkedin.com/in/sumantrak/" target="_blank">
      <img src="assets/img/sumantrak2.jpeg" alt="Sumantrak">
    </a>
    <p>
      <strong><a href="https://www.linkedin.com/in/sumantrak/" target="_blank">Sumantrak Mukherjee</a></strong><br/>
      DFKI
    </p>
  </div>
  <div class="organizer">
    <a href="https://gerritgrossmann.de/" target="_blank">
      <img src="assets/img/gerrit.jpg" alt="Gerrit">
    </a>
    <p>
      <strong><a href="https://gerritgrossmann.de/" target="_blank">Gerrit Grossmann</a></strong><br/>
      DFKI
    </p>
  </div>
  <div class="organizer">
    <a href="https://www.linkedin.com/in/yanan-xin-giscientist/" target="_blank">
      <img src="assets/img/yanan.jpeg" alt="Yanan">
    </a>
    <p>
      <strong><a href="https://www.linkedin.com/in/yanan-xin-giscientist/" target="_blank">Yanan Xin</a></strong><br/>
      TU Delft
    </p>
  </div>
  <div class="organizer">
    <a href="https://jonaswahl.com/" target="_blank">
      <img src="assets/img/jonas.jpeg" alt="Jonas">
    </a>
    <p>
      <strong><a href="https://jonaswahl.com/" target="_blank">Jonas Wahl</a></strong><br/>
      DFKI
    </p>
  </div>
  <div class="organizer">
    <a href="https://dsa.dfki.de/author/sebastian-vollmer/" target="_blank">
      <img src="assets/img/sebastian.jpg" alt="Sebastian">
    </a>
    <p>
      <strong><a href="https://dsa.dfki.de/author/sebastian-vollmer/" target="_blank">Sebastian Vollmer</a></strong><br/>
      DFKI, RPTU
    </p>
  </div>
</div>
