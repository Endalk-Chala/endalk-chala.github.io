---
layout: archive
title: "Contact"
permalink: /contact/
author_profile: true
---

I welcome questions and conversations about my research, publications, teaching, and community-engaged work. You are welcome to contact me about research collaborations, requests for academic papers, information access and language equity, or academic and professional pathways.

## Send a message

You can use the form below to prepare a message. **Selecting “Open email to send” opens your own email application** with the message filled in; it does not submit or store information on this website.

<form id="academic-contact" class="contact-form" style="max-width:650px;margin:1.25rem 0 2rem;">
  <div style="display:flex;gap:1rem;flex-wrap:wrap;">
    <label style="flex:1;min-width:180px;margin-bottom:1rem;">First name <span aria-hidden="true">*</span><input type="text" id="contact-first" required autocomplete="given-name" style="display:block;width:100%;padding:.65rem;margin-top:.35rem;border:1px solid #aaa;border-radius:5px;"></label>
    <label style="flex:1;min-width:180px;margin-bottom:1rem;">Last name <span aria-hidden="true">*</span><input type="text" id="contact-last" required autocomplete="family-name" style="display:block;width:100%;padding:.65rem;margin-top:.35rem;border:1px solid #aaa;border-radius:5px;"></label>
  </div>
  <label style="display:block;margin-bottom:1rem;">Your email <span aria-hidden="true">*</span><input type="email" id="contact-email" required autocomplete="email" style="display:block;width:100%;padding:.65rem;margin-top:.35rem;border:1px solid #aaa;border-radius:5px;"></label>
  <label style="display:block;margin-bottom:1rem;">Message <span aria-hidden="true">*</span><textarea id="contact-message" required rows="6" style="display:block;width:100%;padding:.65rem;margin-top:.35rem;border:1px solid #aaa;border-radius:5px;"></textarea></label>
  <button type="submit" style="background:#2c5780;color:white;border:0;border-radius:5px;padding:.75rem 1.2rem;font:inherit;cursor:pointer;">Open email to send</button>
</form>

<script>
document.getElementById('academic-contact').addEventListener('submit', function (event) {
  event.preventDefault();
  const first = document.getElementById('contact-first').value.trim();
  const last = document.getElementById('contact-last').value.trim();
  const email = document.getElementById('contact-email').value.trim();
  const message = document.getElementById('contact-message').value.trim();
  const subject = 'Academic website inquiry from ' + first + ' ' + last;
  const body = 'From: ' + first + ' ' + last + '\nEmail: ' + email + '\n\n' + message;
  window.location.href = 'mailto:endalk2006@gmail.com?subject=' + encodeURIComponent(subject) + '&body=' + encodeURIComponent(body);
});
</script>

If the form does not open your email application, you can email me directly at [endalk2006@gmail.com](mailto:endalk2006@gmail.com).

---

## Subscribe to research updates

Interested in my publications, open datasets, research resources, and reflections on digital communication, platform governance, AI, language access, and immigrant communities? Subscribe to my writing on **Between Worlds**. Subscription is voluntary and completely separate from contacting me.

<div style="max-width:650px;margin:1.25rem 0;">
  <iframe src="https://endalkchala.substack.com/embed" width="100%" height="320" style="border:1px solid #ddd;border-radius:6px;background:white;" title="Subscribe to Between Worlds on Substack" loading="lazy"></iframe>
  <p style="font-size:.95rem;">If the signup form doesn't display, <a href="https://endalkchala.substack.com/subscribe" target="_blank" rel="noopener noreferrer">subscribe directly on Substack</a>.</p>
</div>

You can unsubscribe from email updates at any time through Substack. Sending a contact inquiry does **not** add you to the subscriber list.
