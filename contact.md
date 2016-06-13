---
layout: default
title: Contact
permalink: /contact/
hero_title: Contact page
hero_lead: Start a conversation
---

{% include hero.html %}

<div class="container">

  <div class="row">
    <div class="col-sm-8">
      <p class="lead">If you're looking for someone to help you plan and build your
        product, or if you need advice on the best way to work on your project, then
        I'd love to have a conversation with you.</p>
    </div>
  </div>
</div>

<div class="next-steps-container container">
  <div class="row">


    <div class="col-sm-3">
      <div class="thumbnail">
        <img src="/assets/bricky-kev.jpg" alt="" title="" class="" height="120" />
        <div class="caption">
          <h3>Kevin Carmody</h3>
          <p>{% include icon-twitter.html username=site.twitter_username %}</p>
          <p>07870332981</p>
        </div>
      </div>
    </div>

    <div class="col-sm-6  col-sm-offset-0">
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
          <button type="submit" class="btn btn-primary">Submit</button>
        </div>
      </form>
    </div>


  </div>
</div>
