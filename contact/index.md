---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: page
title: Contact
---
If you’d like to get in touch with Leeds Community Homes you can contact us via [Twitter](https://twitter.com/leedscommhomes), [Facebook](https://www.facebook.com/LeedsCommunityHomes/) or by sending a message through the form below and we’ll get back to you.

<form method="POST" action="https://form.letsdance.agency/57nQPDw4" class="contact-form">
  <h2 class="form-title">Send us a message</h2>
  <input type="text" name="_honey" value="" style="display: none;">
  <input type="hidden" name="_subject" value="Message from leedscommunityhomes.org.uk" >
  <input type="email" name="_replyto" placeholder="Your email" required="">
  <input type="text" name="name" placeholder="Your name" required="">
  <textarea rows="7" name="message" placeholder="Your message" required=""></textarea>
  <input type="submit" value="Send">
</form>


<script>
  if (document.forms[0] && window.FormData) {

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