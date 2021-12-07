# Event Prioritization
## How to make a first data-driven assessment on events for sponsoring, participation, contribution, speaking

This process was an implementation of a less-biased (TM) decision matrix, that I designed in my first weeks as a Porgram Manager in DevRel at Postman. It is not without flaws, and can never be the single decision-making power for a contribution of any form to an event. But it can give you a first glance on matching your priorities, especially if you have to handle more than 10 events per calendar year. It is also highly adaptable, once you understood the concept and can do some coding.

## The Process
A) Data Collection
1) Set up a Survey Tool (in our case [this Demo Typeform](https://jpr72681q14.typeform.com/to/jNUN5xMj)). You will need a paid plan for this unfortunately. The data collected through this form currently includes:
 - Submitter's name
 - Event name
 - Calendar year
 - Homepage
 - Event type (in-person, virtual, etc)
 - Topic
 - Interest of Organisers (commercial or community)
 - Location, country, continent
 - Start & end date
 - # of attendees
 - Attendance fee in USD
 - Sponsoring packages
 - Call for Proposal details
 - Code of Conduct details
 - Previous participation of colleagues
 - Competitive participation
 - # Speakers and representation of marginalized groups
 - Colleagues as speakers
 - Qualitative feedback
 - Opportunity for focus topics
 - Online availability of sessions post-event

2) Set up your Airtable Base. You can copy and start from [this one](https://airtable.com/invite/l?inviteId=invLXVX5y41POso3x&inviteToken=6eb7c9d7a336bd50a17bd26ec10e74db54e1bb859510c79a873351f147d74f80&utm_source=email), as it already has the necessary table structure set up.
4) Get your [Airtable API key from here](https://airtable.com/account). Leave that windows open. You'll need the API key once again in another step.
3) [Connect Typeform to Airtable](https://www.typeform.com/help/a/send-data-to-airtable-with-a-typeform-360029263292/). You'll need the Alternatively fill the Airtable manually or import existing data.
4) Clean and complete data in Airtable.
5) Import (may not be up-to-date) of [fork](https://learning.postman.com/docs/collaborating-in-postman/version-control-for-collections/)(easier) [this Postman collection](https://www.postman.com/lichtsucht/workspace/demo-space/collection/11948645-a6307c6d-39dc-457a-bf19-455158425ff5?ctx=documentation).
4) Use the Airtable key from above or re-fetch your [Airtable API key here](https://airtable.com/account).
5) Run the collection in Postman's Runner.
6) Watch Airtable how the additional fields Internal Rating and Sponsoring Qualified populate. Enjoy! 
