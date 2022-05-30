# Event Prioritization
## How to make a first data-driven assessment on events for sponsoring, participation, contribution, speaking

This process was an implementation of a less-biased (TM) decision matrix, that I designed in my first weeks as a Porgram Manager in Developer Relations at Postman, the developer tooling company. It is not without flaws, and can never be the single decision-making power for a contribution of any form to an event. But it can give you a first glance on matching your priorities, especially if you have to handle more than 10 events per calendar year. It is also highly adaptable, once you understood the mechanism and can do some coding.

[Here's the step-by-step guide posten on dev.to](https://dev.to/postman/a-devrel-approach-to-prioritising-events-3d7m)

## The Setup Process
1) Set up a Survey Tool (in our case [this Demo Typeform](https://jpr72681q14.typeform.com/to/jNUN5xMj)). On Typeform you will need a paid plan for this unfortunately, as it's beyond the free 10 questions. The data collected through this form currently includes:
 - Submitter's name
 - Event name
 - Calendar year
 - Homepage
 - Event type (in-person, virtual, etc)
 - Topic
 - Interest of Organisers (commercial or community)
 - Location, country, continent
 - Start & end date
 - \# of attendees
 - Attendance fee in USD
 - Sponsoring packages
 - Call for Proposal details
 - Code of Conduct details
 - Previous contribution of colleagues/company
 - Competitive contribution
 - \# of speakers and representation of marginalized groups
 - Colleagues as speakers
 - Qualitative feedback
 - Opportunity for focus topics
 - Online availability of sessions post-event

2) Set up your Airtable Base. You can copy and start from [this one](https://airtable.com/shrj4wLwYro6MbDoj), as it already has the necessary table structure set up.
4) Copy your [Airtable API key from here](https://airtable.com/account). Leave that window open. You'll need the API key in another step.
3) [Connect Typeform to Airtable](https://www.typeform.com/help/a/send-data-to-airtable-with-a-typeform-360029263292/). This is a bit awkward as you can;t edit the connection, just delete and re-connect. Alternatively fill the Airtable manually or import from e.g. a spreadsheet.
4) Clean up and complete data in Airtable. The more data you have the more exact the result will be.
5) [Import](https://github.com/jansche/event-prioritization/blob/main/Postman_Collection_EventViability.json) (may not be up-to-date) of better [fork](https://learning.postman.com/docs/collaborating-in-postman/version-control-for-collections/) [this Postman collection](https://www.postman.com/lichtsucht/workspace/demo-space/collection/11948645-a6307c6d-39dc-457a-bf19-455158425ff5?ctx=documentation).
4) Use the same Airtable key from above or re-fetch your [Airtable API key here](https://airtable.com/account).
5) Update the AirtableId and Table Variable in the Collection. 
6) Run the Collection in Postman's Runner.
7) Watch Airtable while Postman fills the additional fields Internal Rating and Sponsoring Qualified populate. Enjoy! 
8) Now fine tuning, run, repeat. 

## Continuous usage
Whenever I get into discussing events with colleagues I ask them to help me out and fill out the form so we can consider the event in a less-biased (TM) way. Although the form is exhausting to complete, they normally do for the events they care about. I also ask event organisers who approach me with a sponsoring request to fill out the form. They are nromally happy to do so and get a roughh picture of what is important to us. If they leave an e-mal address in the form, I normally make sure to follow up with them.
