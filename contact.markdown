---
layout: page
title: Contact
permalink: /contact/
---

# Get in Touch

Feel free to reach out using the form below. I'll get back to you as soon as possible.
You can also contact me on [LinkedIn](https://www.linkedin.com/in/samuel-louviot) or see my [GitHub](https://github.com/Sam54000).

<form action="https://formspree.io/f/mpwqgbnd" method="POST">
  <div style="margin-bottom: 20px;">
    <label for="email" style="display: block; margin-bottom: 5px;">Email:</label>
    <input class="input-field" type="email" id="email" name="email" required>
  </div>

  <div style="margin-bottom: 20px;">
    <label for="message" style="display: block; margin-bottom: 5px;">Message:</label>
    <textarea class="input-field" id="message" name="message" rows="6" required></textarea>
  </div>

  <button class="button" type="submit">Send Message</button>
</form>

<style>
  .input-field {
    width: 100%;
    padding: 8px;
    border: none;
    background-color: var(--bg3);
    color: var(--fg);
  }
  .input-field:focus {
    border: 1px solid var(--light-green);
    outline: none;
    background-color: var(--bg4);
  }

  .button {
    background-color: var(--blue);
    color: white;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
  }

  .button:hover{
    background-color: var(--orange);
  }
</style>
<script>
  var form = document.querySelector('form');
  form.addEventListener('submit', function(e) {
    e.preventDefault();
    var button = form.querySelector('button');
    
    button.disabled = true;
    button.textContent = 'Sending...';
    
    fetch(form.action, {
      method: 'POST',
      body: new FormData(form),
      headers: {
        'Accept': 'application/json'
      }
    }).then(response => {
      console.log('Response status:', response.status);
      return response.json().then(data => {
        console.log('Response data:', data);
        if (response.ok) {
          form.reset();
          button.textContent = 'Message Sent!';
          setTimeout(() => {
            button.disabled = false;
            button.textContent = 'Send Message';
          }, 3000);
        } else {
          throw new Error(data.error || 'Submission failed');
        }
      });
    }).catch(error => {
      console.error('Detailed error:', error);
      button.disabled = false;
      if (error.message.includes('not activated')) {
        button.textContent = 'Please Check Email to Activate';
        alert('Please check your email to verify the form first. Formspree requires email verification for first-time use.');
      } else {
        button.textContent = 'Error! Try Again';
      }
    });
  });
</script> 