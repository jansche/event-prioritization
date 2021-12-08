---
title: A DevRel Approach to Prioritising Events for Contribution
published: false
description: How to make a first data-driven assessment on events for sponsoring, participation, contribution, speaking
tags: productivity, career, tutorial
//cover_image: https://direct_url_to_image.jpg
---

## TL;DR 
If your role includes decision-making on industry or community events in DevRel or Dev Marketing, this article can help you go through your own lists of events and rate them against each other, so you will be able to include a data-driven approach when deciding on contributing (sponsoring, speaking, volunteering, participating) and be less biased through previous participation or sparkly advertising. This process takes a heavy stance on diversity, equity and inclusion and so should you.

## Objective
This is meant as a step-by-step guide to automate a data-driven assessment of events for sponsoring, participation, contribution and speaking. The event list can be dynamic and gathered through a form request tool, or imported from existing assets like a gSheet, Excel or Airtable. At the end of this guide, you'll be able to inspect a list of individually sourced events with supporting data for prioritising your time and budget. Whether you want to pick the top five or the best 30 that fit your (budget|focus topics) doesn't matter.

## Disclaimer
A) This full process is work in progress. 
B) The weight of different factors that heavily influence the outcome in form of a _Rating_ is totally up to your customisation. We don't suggest by any means to keep the weighting as is, but trial and error to best reflect your company's values and preferences. This customisation requires a certain level of programming knowledge as you will have to modify and manipulate arrays, variables, loops and conditions.

## The Step-by-Step Setup Guide
A brief version of this guide can be found on [GitHub](https://github.com/jansche/event-prioritization).

1. Defining a data source. 
  In our case, it will be a Typeform request from to collect all relevant data, as it is most flexible and shareable as well as able to interact with Airtable through an existing Connect procedure (although it doesn't have the best user experience).
  Alternatively you could decide to just import data to Airtable, but since this should be an ongoing business process, a form has been the better choice for us. You could still initially start with data from existing sheets. See [import options in Airtable](to fill still). Or manually fill the Airtable base.

2. Clone this [Airtable base](https://airtable.com/shrj4wLwYro6MbDoj) into your own workspace on Airtable. 
![Screenshot of an Airtable base pointing the viewer towards where to find the "Copy base" action on the top right of the web page](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/8vfsy9qootuqc1bawf6h.png)
  This base contains some incomplete and also outdated sample data. Replace this sample data as soon as possible with your own data.

3. Set up the request form like this [Typeform](https://jpr72681q14.typeform.com/to/jNUN5xMj). My apologies, there's currently no way to share a template of this with you. Field names should ideally correspond to (but don't have to be the exact same name as) Airtable columns.
  ![Screenshot of a Create screen at Typeform, showing all the form fields and their types](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1ygwkkghjyayayyumru9.png)
  I suggest to start with a smaller set of questions (begin with 3 or 4, and not to add custom questions just yet. Do that once you implemented the whole template process and feel confident enough to also adapt the code behind. Otherwise you'll end up with a bunch of answers that you don't make use of.

4. Back to Airtable, generate and copy [your API key](https://airtable.com/account) from your account settings.
  ![Screenshot of the section of the page where to find your account information, top right](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/wvoi3e1g8jhcnp9iw9x3.png)
  ![Screenshot of the "Generate API Key" dialogue on the main profile page of Airtable](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hrfwzd6az4kxiwwcs7hf.png)
  ![Screenshot of the API Key section with a generated API Key](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jepdz0g4nnicawqktxau.png)
Leave that window open, you'll need the API Key in another step in this guide again.

5. Now you can connect Typeform with Airtable. All of the form replies will go into Airtable. There's just one caveat. The process of connecting the two is somewhat awkward, and updating an existing connection isn't possible. You can;t even reload while setting up. But see yourself.
  ![Screenshot of the Connect tab in Typeform with a filtered view on the Airtable integration, showing a connect button.](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rmuusktqha9k0tos72pv.png)
Now select Connect, and Typeform will ask you to log in to Airtable and provide your API Key.
After that, your good to go and match questions with fields in Airtable.
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/m0x3drmk5mcavp8em5nx.png)
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tn312t81xzcvuh1k5k5p.png)
  This process is why I mentioned to start with a few questions first. It looks fancy first, but turns out to be awkward. Beyond awkward. Once you run into a mismatch, you have to start over. From. The. Beginning.
  And yes, you will run into mismatches. More than once. Twitter mention me (@jansche) if you don't.  
  Once you're done and activated the integration, data will feed into Airtable. Do a test run through answering your own form.

6. It's Postman time! 
  [Create a free Postman account](https://learning.postman.com/docs/getting-started/postman-account/#signing-up-for-a-postman-account) if you haven't and then [fork this Postman collection](https://www.postman.com/lichtsucht/workspace/demo-space/collection/11948645-a6307c6d-39dc-457a-bf19-455158425ff5?ctx=documentation) into your own workspace.
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dg3xzh4qjrwv0qy7bl4o.png)
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nxxumw6z1w9ek6ug91xf.png)

7. Use your Airtable API Key in Postman. For now, it would be ok to just paste it where it says {{APIKey}} in the main view of the collection.
 ![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v4iupc7elp7n95e99oeh.png)
In general, you should store API keys in a dedicated Environment, and, if you're going to share your environment, also only as "Current Value". 

8. In the collection's main view, head over to the Variables tab, as you will need to update "AirtableId" and Table variables with your Airtable ID from the URL, and the name of your table.
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/og45b39flib2nwgds1c2.png)
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/nzkpmojgzdt7layu1txm.png)
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hhokcxh781q3n98d0ci1.png)
  You can leave the Event Name as is, if you're batch processing all entries in Airtable, setting this variable initially doesn't do much.

9. SAVE. You have to hit 💾 Save or Control-S/Command-S to make this changes take effect.

10. Up next is to run the collection in Runner. YAY! Cross your fingers. Buckle up. If everything went ok, we'll see some results being magically populated in Airtable in a moment. 
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/t0arz0r3xdsda4ucsmgu.png)

11. We're done! Not quite yet, there's still plenty to fine tune. But you got it working! Hint: take a look into 
the "Calculate Rating Existing Event" request. All of the calculation is happening in the "Tests" section of this request. 
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ousfzl5jp1idv2ub6s8e.png)
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/2ly1wbowdpn2svp2ysny.png)
But that's a different story and will be covered in a separate article soon.

Happy rating, and don't forget to make this only one factor of your decision on contributing to an event or not.

Jan
