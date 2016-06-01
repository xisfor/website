---
layout: post
title:  "Serverless contact form with AWS Lambda"
date:   2016-06-01
categories: aws lambda api tech
permalink: /blog/:year/:month/:day/:title/
---
Static sites are great. They're really really great. Except for one minor issue... they're really static. Sometimes you have a little bit that needs a server, like a contact form!

I was talking about this with [a friend](http://www.alexdunne.net/) the other day, and we joked about using AWS Lambda. It's supposed to be "serverless", in that you can just run scripts. Oh how we laughed. Then, when his back was turned, I just went for it.

It's actually pretty simple. You need more than just Lambda, you'll also need SES and API Gateway. It's all really straight forward though.

Lambda can (at time of writing - May 2016) only run Java, Python or Node.js. I went for the latter.

This is the Lambda Javascript you'd need

{% highlight javascript %}
var aws = require('aws-sdk');
var ses = new aws.SES({
  accessKeyId: 'ACCESSKEEEEEY',
  secretAccesskey: 'SECRETKEEEEYYYY',
  region: 'eu-west-1'
});

var sendEmail = function(emailDetails, context){
  if (!emailDetails.email) {
    context.fail("Please provide at least an email address");
    return;
  }

  var messageParts = [];

  messageParts.push("Email Address: " + emailDetails.email);
  if (emailDetails.message) {
    messageParts.push("Message: \n" + emailDetails.message);
  }

  var params = {
    Destination: {
      ToAddresses: [ 'Team Hi <hi@xisfor.tech>' ]
    },
    Message: {
      Body: { Text: { Data: messageParts.join("\r\n"), Charset: 'UTF-8' } },
      Subject: { Data: "You've got a message", Charset: 'UTF-8' }
    },
    Source: "Contact Form <hi@xisfor.tech>",
    ReplyToAddresses: [ "hi@xisfor.tech" ]
  };

  ses.sendEmail(params, function(err, data) {
    if (err) {
      console.log(err, err);
      context.fail('Problem: ' + err);
    } else {
      console.log("Email send confirmed with following", data);
      context.succeed('Thanks for getting in contact');
    }
  });
}

exports.handler = function(event, context) {
  var emailDetails = {
    "email": event.email,
    "message": event.message
  };
  sendEmail(emailDetails, context)
};
{% endhighlight %}

And the test event for this would be:

{% highlight javascript %}
{
  "email": "kevin+lmbtester@xisfor.tech",
  "message": "yo yo testing"
}
{% endhighlight %}

When you start to test, you'll notice that your sending email isn't validated in SES. This is much simpler to validate than other similar services. Just head over to SES, pick Email Addresses from Identity Management on the left and verify your intended send email.

Next up, head over to API gateway, create a new API. Add a resource with the route you want to target your form at. Create a POST method for that resource with a Lambda integration.. your Lambda integration.

You should also add an OPTIONS method as many AJAX libs (e.g. jQuery) will hit this as a preflight request. If it fails, they won't do the POST request!

Make sure you enable CORS on your API. And don't forget to redeploy after any changes.

If you haven't already, deploy your API. The deployment stages give you the endpoint of your API. For example, `https://zio6ulwrtc.execute-api.eu-west-1.amazonaws.com/prod`

Finally, you can do the form, where you just need to set the form's ACTION to be the API resource you've created.

Bish-bash-bosh. Serverless contact forms.
