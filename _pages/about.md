---
layout: default
title: STAR Group
permalink: /
---

# ⭐ Space-Time cAusal Reading (STAR) Group

Welcome to the STAR Group — a reading group dedicated to exploring **causal inference in spatio-temporal systems**, including methodological, theoretical, and applied perspectives. We meet regularly to discuss cutting-edge research and foster interdisciplinary collaboration.

---
## 🗓️ Schedule

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
    <p>We currently have no scheduled sessions. Want to speak at a future session? <a href="mailto:contact@yourdomain.com">Contact us here</a>.</p>
  </div>
{% endif %}

### Previous Sessions
<p>Below are the most recent sessions. Click "Show All Sessions" to view the full history.</p>

<div style="overflow-x:auto;">
<table style="width: 100%; border-collapse: collapse;">
  <thead>
    <tr>
      <th style="text-align: left; padding: 8px;">Date</th>
      <th style="text-align: left; padding: 8px;">Topic</th>
      <th style="text-align: left; padding: 8px;">Paper</th>
      <th style="text-align: left; padding: 8px;">Speaker</th>
      <th style="text-align: left; padding: 8px;">Slides</th>
      <th style="text-align: left; padding: 8px;">Recording</th>
    </tr>
  </thead>

  <tbody>
  {% assign reversed_sessions = site.data.schedule | reverse %}
  {% assign visible = reversed_sessions | slice: 0, 7 %}
  {% for session in visible %}
    <tr>
      <td style="padding: 8px;">{{ session.date }}</td>
      <td style="padding: 8px;">{{ session.topic }}</td>
      <td style="padding: 8px;"><a href="{{ session.paper }}">Paper</a></td>
      <td style="padding: 8px;">{{ session.speaker }}</td>
      <td style="padding: 8px;"><a href="{{ session.slides }}">Slides</a></td>
      <td style="padding: 8px;"><a href="{{ session.recording }}">Recording</a></td>
    </tr>
  {% endfor %}
  </tbody>

  <tbody id="older-sessions" style="display: none;">
  {% assign older = reversed_sessions | slice: 7, reversed_sessions.size %}
  {% for session in older %}
    <tr>
      <td style="padding: 8px;">{{ session.date }}</td>
      <td style="padding: 8px;">{{ session.topic }}</td>
      <td style="padding: 8px;"><a href="{{ session.paper }}">Paper</a></td>
      <td style="padding: 8px;">{{ session.speaker }}</td>
      <td style="padding: 8px;"><a href="{{ session.slides }}">Slides</a></td>
      <td style="padding: 8px;"><a href="{{ session.recording }}">Recording</a></td>
    </tr>
  {% endfor %}
  </tbody>
</table>
</div>

<button id="toggle-sessions" class="btn" style="margin-top: 1em; background-color: #007acc; color: white; border: none; padding: 10px 15px; border-radius: 4px; cursor: pointer;">
  Show All Sessions
</button>

<script>
  const toggleBtn = document.getElementById("toggle-sessions");
  const olderRows = document.getElementById("older-sessions");

  toggleBtn.addEventListener("click", () => {
    if (olderRows.style.display === "none") {
      olderRows.style.display = "table-row-group";
      toggleBtn.textContent = "Hide Older Sessions";
    } else {
      olderRows.style.display = "none";
      toggleBtn.textContent = "Show All Sessions";
    }
  });
</script>
<!-- ##  Schedule

<p>Below are the most recent sessions. Click "Show All Sessions" to view the full history.</p>

<table>
  <thead>
    <tr>
      <th>Date</th>
      <th>Topic</th>
      <th>Paper</th>
      <th>Speaker</th>
      <th>Slides</th>
      <th>Recording</th>
    </tr>
  </thead>

  <tbody>
  {% assign reversed_sessions = site.data.schedule | reverse %}
  {% assign visible = reversed_sessions | slice: 0, 7 %}
  {% for session in visible %}
    <tr>
      <td>{{ session.date }}</td>
      <td>{{ session.topic }}</td>
      <td>{{ session.speaker }}</td>
      <td><a href="{{ session.paper }}">Paper</a></td>
      <td><a href="{{ session.slides }}">Slides</a></td>
      <td><a href="{{ session.recording }}">Recording</a></td>
    </tr>
  {% endfor %}
  </tbody>

  <tbody id="older-sessions" style="display: none;">
  {% assign older = reversed_sessions | slice: 7, reversed_sessions.size %}
  {% for session in older %}
    <tr>
      <td>{{ session.date }}</td>
      <td>{{ session.topic }}</td>
      <td>{{ session.speaker }}</td>
      <td><a href="{{ session.paper }}">Paper</a></td>
      <td><a href="{{ session.slides }}">Slides</a></td>
      <td><a href="{{ session.recording }}">Recording</a></td>
    </tr>
  {% endfor %}
  </tbody>
</table>

<button id="toggle-sessions" style="margin-top: 1em;">Show All Sessions</button>

<script>
  const toggleBtn = document.getElementById("toggle-sessions");
  const olderRows = document.getElementById("older-sessions");

  toggleBtn.addEventListener("click", () => {
    if (olderRows.style.display === "none") {
      olderRows.style.display = "table-row-group";
      toggleBtn.textContent = "Hide Older Sessions";
    } else {
      olderRows.style.display = "none";
      toggleBtn.textContent = "Show All Sessions";
    }
  });
</script> -->

> 📝 *Sessions are bi-weekly on Wednesday 3pm CET.*

---

## 👥 Organizers

<div class="organizers">
  <div class="organizer">
    <img src="assets/img/organizers/alex.jpg" alt="Sumantrak" width="100">
    <p><strong>Sumantrak Mukherjee</strong><br/>DFKI</p>
  </div>
  <div class="organizer">
    <img src="assets/img/organizers/lee.png" alt="Gerrit" width="100">
    <p><strong>Gerrit Grossmann</strong><br/>DFKI</p>
  </div>
  <div class="organizer">
    <img src="assets/img/organizers/nora.jpg" alt="Yanan" width="100">
    <p><strong>Yanan Xin</strong><br/>TU Delft</p>
  </div>
  <div class="organizer">
    <img src="assets/img/organizers/nora.jpg" alt="Jonas" width="100">
    <p><strong>Jonas Wahl</strong><br/>DFKI</p>
  </div>
  <div class="organizer">
    <img src="assets/img/organizers/nora.jpg" alt="Sebastian" width="100">
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

