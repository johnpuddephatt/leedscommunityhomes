---
layout: page
date: 2016-03-23T10:20:00.000+00:00
title: Contact
menu: footer

---
If you’d like to get in touch with Leeds Community Homes you can call us on <a href="tel:0113 450 8905">0113 450 8905</a>, follow us on [Twitter](https://twitter.com/leedscommhomes) or [Facebook](https://www.facebook.com/LeedsCommunityHomes/), or send us a message through the form below and we’ll get back to you. *Please note that currently we cannot take calls due to staff working remotely during COVID19.

<script src="https://www.google.com/recaptcha/api.js" async defer></script>
<form method="POST" action="https://form.letsdance.agency/57nQPDw4" class="contact-form">
<h2 class="form-title">Send us a message</h2>
<input type="text" name="_honey" value="" style="display: none;">
<input type="hidden" name="_subject" value="Message from leedscommunityhomes.org.uk" >
<input type="email" name="_replyto" placeholder="Your email" required="">
<input type="text" name="name" placeholder="Your name" required="">
<textarea rows="7" name="message" placeholder="Your message" required=""></textarea>
<div class="g-recaptcha" data-sitekey="6LdNn1AUAAAAAA-VLy7CCzufqQi7EhPyoWQwcHIM"></div>
<input type="submit" value="Send">
</form>

<script>
if (document.forms\[0\] && window.FormData) {

    var message = new Object();
    message.loading = 'Loading...';
    message.success = 'Thank you. Message received!';
    message.failure = 'Whoops! There was a problem sending your message.';
    
    var form = document.forms[0];
    var formAction = form.getAttribute("action");
    var statusMessage = document.createElement('div');
    statusMessage.className = 'status';
    
    // Set up the AJAX request
    var request = new XMLHttpRequest();
    request.open('POST', formAction, true);
    request.setRequestHeader('accept', 'application/json');
    
    // Listen for the form being submitted
    form.addEventListener('submit', function(evt) {
    
        evt.preventDefault();
      form.insertAdjacentElement('beforeend', statusMessage);
    
        // Create a new FormData object passing in the form's key value pairs (that was easy!)
        var formData = new FormData(form);
    
        // Send the formData
        request.send(formData);
    
        // Watch for changes to request.readyState and update the statusMessage accordingly
        request.onreadystatechange = function () {
    
        // <4 =  waiting on response from server
        if (request.readyState < 4)
            statusMessage.innerHTML = message.loading;
    
        // 4 = Response from server has been completely loaded.
        else if (request.readyState === 4) {
    
            // 200 - 299 = successful
            if (request.status == 200 && request.status < 300)
                statusMessage.innerHTML = message.success;
            else
              statusMessage.innerHTML = message.failure;
        }
        }
    });

}
</script>