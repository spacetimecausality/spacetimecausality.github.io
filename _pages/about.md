---
layout: default
title: STAR Group
permalink: /
---

<h1 style="display: flex; align-items: center; gap: 0.4em;">
  <img src="/assets/img/STAR.png" alt="STAR Logo" style="height: 1.5em;">
  <span>
    <strong>STaR</strong>:
    <span class="text-primary">S</span>pace-
    <span class="text-primary">T</span>ime 
    C<span class="text-primary">a</span>usality 
    <span class="text-primary">R</span>eading Group
  </span>
</h1>

Welcome to the STAR Group — a reading group dedicated to exploring **causal inference in spatio-temporal systems**, including methodological, theoretical, and applied perspectives. We meet regularly to discuss cutting-edge research and foster interdisciplinary collaboration.

---
## 🗓️ Schedule
---

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
    <p><strong>Paper:</strong> <a href="{{ next_session.paper }}">{{ next_session.paper }}</a></p>
  </div>
{% else %}
  <div class="no-session">
    <h3>No Upcoming Sessions</h3>
    <p>
      We currently have no scheduled sessions. Want to speak at a future session?
      <a href="spacetimecausality@gmail.com">Contact us here</a>.
    </p>
  </div>
{% endif %}

---

### 🔙 Previous Sessions

<p>All past sessions are listed below. Slides and recordings available upon request.</p>

{% assign today = 'now' | date: "%Y-%m-%d" %}
{% assign past_sessions = "" | split: "" %}

{% for session in site.data.schedule %}
  {% assign session_date = session.date | date: "%Y-%m-%d" %}
  {% if session_date < today %}
    {% assign past_sessions = past_sessions | push: session %}
  {% endif %}
{% endfor %}

{% assign sorted_sessions = past_sessions | sort: "date" | reverse %}

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
      {% for session in sorted_sessions %}
        <tr>
          <td style="padding: 8px; white-space: nowrap;">{{ session.date }}</td>
          <td style="padding: 8px;">{{ session.topic }}</td>
          <td style="padding: 8px;"><a href="{{ session.paper }}">Paper</a></td>
          <td style="padding: 8px;">{{ session.speaker }}</td>
        </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

### Upcoming Planned Sessions

<p>Here are the upcoming sessions scheduled. Slides and recordings will be shared after the session.</p>

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
{% endif %}

---

> 📝 *Sessions are fortnightly on Wednesday at 3pm CET.*


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
    <img src="assets/img/sumantrak2.jpeg" alt="Sumantrak">
    <p><strong>Sumantrak Mukherjee</strong><br/>DFKI</p>
  </div>
  <div class="organizer">
    <img src="assets/img/gerrit.jpg" alt="Gerrit">
    <p><strong>Gerrit Grossmann</strong><br/>DFKI</p>
  </div>
  <div class="organizer">
    <img src="assets/img/yanan.jpeg" alt="Yanan">
    <p><strong>Yanan Xin</strong><br/>TU Delft</p>
  </div>
  <div class="organizer">
    <img src="assets/img/jonas.jpeg" alt="Jonas">
    <p><strong>Jonas Wahl</strong><br/>DFKI</p>
  </div>
  <div class="organizer">
    <img src="assets/img/sebastian.jpg" alt="Sebastian">
    <p><strong>Sebastian Vollmer</strong><br/>DFKI, RPTU</p>
  </div>
</div>


<style>
.organizers {
  display: flex;
  gap: 2rem;
  flex-wrap: wrap;
  margin-bottom: 2rem;
}
.organizer {
  text-align: center;
  max-width: 120px;
}
.organizer img {
  border-radius: 50%;
  box-shadow: 0 0 10px rgba(0,0,0,0.15);
}
</style>

---

## 📬 Join Us

Want to present, suggest papers, or join our mailing list?  
Reach out to **spacetimecausality@gmail.com** or check our [GitHub repo](https://github.com/YOUR-ORG/star-group).

