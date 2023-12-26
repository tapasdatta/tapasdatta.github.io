---
layout: page
title: Contact
permalink: /contact/
---

<div class="form-box">
  <div class="contact-head">
    {% if site.contact.description %}
    <p class="page-description">{{site.contact.description}}</p>
    {% endif %}
  </div>
  <form class="form" id="contact-form" action="{% if site.contact.email %}https://formspree.io/{{site.contact.formspree}}{% else %}#{% endif %}" method="POST">
    <div class="form__group">
      <label class="form__label screen-reader-text" for="form-name">Your Name</label>
      <input class="form__input" id="form-name" type="text" name="name" placeholder="Name" required>
    </div>
    <div class="form__group">
      <label class="form__label screen-reader-text" for="form-email">Your Email</label>
      <input class="form__input" id="form-email" type="email" name="_replyto" placeholder="Email" required>
    </div>
    <div class="form__group">
      <label class="form__label screen-reader-text" for="form-text">Your Message</label>
      <textarea class="form__input" id="form-text" name="text" rows="10" placeholder="Message" required></textarea>
    </div>
    <div class="form__group">
      <button class="button" type="submit">Send Message</button>
    </div>
    <p id="form-status"></p>
  </form>
</div>
<script>
    var form = document.getElementById("contact-form");
    
    async function handleSubmit(event) {
      event.preventDefault();
      var status = document.getElementById("form-status");
      var data = new FormData(event.target);
      fetch(event.target.action, {
        method: form.method,
        body: data,
        headers: {
            'Accept': 'application/json'
        }
      }).then(response => {
        if (response.ok) {
          status.innerHTML = "Thanks for your message! I'll respond you shortly.";
          form.reset()
        } else {
          response.json().then(data => {
            if (Object.hasOwn(data, 'errors')) {
              status.innerHTML = data["errors"].map(error => error["message"]).join(", ")
            } else {
              status.innerHTML = "Oops! There was a problem submitting your form"
            }
          })
        }
      }).catch(error => {
        status.innerHTML = "Oops! There was a problem submitting your form"
      });
    }
    form.addEventListener("submit", handleSubmit)
</script>