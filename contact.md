---
layout: page
title: Contact
permalink: /contact/
---


<div class="row">
  <div class="col-sm-8">
    <p class="lead">If you're looking for someone to help you plan and build your
      product, or if you need advice on the best way to work on your project, then
      I'd love to have a conversation with you.</p>
  </div>
</div>

<div class="row next-steps-container">

  <div class="col-sm-6">
    <div id="form-submit-response"></div>

    <form accept-charset="UTF-8"
          action="https://zio6ulwrtc.execute-api.eu-west-1.amazonaws.com/prod/xisforcontact"
          method="POST"
          id="contact-form">

      <div class="form-group">
        <label for="email-input">Your email address</label>
        <input name="email" type="email" class="form-control" id="email-input" placeholder="Email">
      </div>

      <div class="form-group">
        <label for="body-input">Your request</label>
        <textarea name="message" id="body-input" placeholder="Request" class="form-control" rows="6"></textarea>
      </div>

      <div class="form-group">
        <button type="submit" class="btn btn-default">Submit</button>
      </div>
    </form>
  </div>

</div>
