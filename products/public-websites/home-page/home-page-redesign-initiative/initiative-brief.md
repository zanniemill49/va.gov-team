## Initiative Brief – Home page redesign initiative 

[Overview](#overview)

[Problems to solve](#problems-to-solve)

[Desired outcomes](#desired-outcomes)

[Measuring success](#measuring-success)

[Assumptions and risks](#assumptions-and-risks)

[Prioritization](#prioritization)

[Summary of changes](#summary-of-changes)

[Next steps](#next-steps)

- [Research](#research)

- [Connection to authenticated experience](#connection-to-authenticated-experience)

[Launch planning](#launch-planning)

- [Collaboration cycle](#collaboration-cycle)

- [Go-to-market strategy](#go-to-market-strategy)

- [Timeline](#timeline) 

[Screenshots](#screenshots)

## Overview
- Although the redesign was planned as a series of smaller changes, given the strong evidence for change and experimental nature of our work, it was decided to go straight to the planned Step 3 design for the first build. Further refinement will be informed by Veteran research before changes are moved to production.
- So that users of assistive technology can participate in usability testing of the new design, the iteration will be built as functional code in a subdomain on staging. Because the page will not receive visitor traffic outside of user testing, no data layer has been applied. 
- This "first build" will be complete with internal links vs. just a static Preview home page with links out to Prod sub-pages 

## Problems to solve
- In March 2022, ~10% of users logged in to VA.gov, which means the majority of users do not benefit from the personalized experience.
- The home page has a very low engagement (measured by event rates), particularly for
  - VAntage Point blog articles on the home page
  - top tasks in the 4 panels 
- The text-heavy current experience increases cognitive load and discourages engagement. 
- The current UX design was optimized for viewability across Desktop and Mobile, limiting the number of links to five in each of the four top task boxes. This limitation has made it difficult to respond to the expanding benefit and program landscape and stakeholder requests. 

## Desired Outcomes
**Desired user outcomes**
- As a Veteran I want to be able to access tools and processes quickly and easily so that I can manage my own VA benefits 
- As a Veteran, caregiver, family member, etc, I want to be able to learn about the different benefits available to me including eligibility etc. so that I can apply to these benefits.
- As a secondary audience to VA.gov (VSO, Member of Congress, News) I need to understand where on VA.gov I should go to manage and learn activities appropriate to my needs 
- Veterans have increased access to self-service tools through an elevated login funnel 

**Undesired User Outcomes**
- Decrease in engagement with the most popular Top Tasks might be concerning, but would have to be viewed in context of overal engagement patterns.
- Search behavior should be monitored for signs that prominent placement of Search in the page is attracting users for use cases that would be better served by some other path/product.

**Desired Business Outcomes**
- Stakeholders can promote and give visibility to new products and services
- More traffic from the home page to the VAntage Point blog
- More logins

---
## Measuring Success

Our goal is to test ideas for making it easier to find and interact with the elements of the page that positively impact Veterans by improving the usefulness of what matters to them and removing clutter and distractions. ***These experiments are not going to be deployed in production, but rather on a publicly accessible subdomain of va.gov.***

We will work through the Collaboration Cycle to determine how to measure outcomes in a non-production environment.

### Expected outcomes
- Increase engagement with Veteran-relevant VAntage Point blog articles by changing content placement (measured by increase in click through rate) 
- Increase use of personalized experience (measured by increase in sign-in/sign-up rates) 
- Decrease time to take action

### Key Performance Indicators (KPIs)

**Because we are going to run this experiment on a subdomain of va.gov, we will need to work closely with the Analytics team to design the experiment and KPIs. We will need to design the experiment around a lack of historical data on subdomain traffic and a current lack of A/B testing capability.**

---

## Assumptions and risks

**Value Risks** (will people use it): 
  - The use of the home page itself is a given.
  - The case for change is very strong, given engagement gaps with the current design.
**Usability Risks** (can people figure out how to use it):
  - It may be unclear that "Search" is searching content on VA.gov. The list of other search tools below complicates what exactly they're searching when they type something into that section.
  - The "Popular" heading may be unclear as to what exactly this list is for. (Popular what?)
  - The "other search tools" may be unclear as to where someone would actually be going when they click on those links, and what information they would find there.
  - There is a lot of copy in the "Browse benefits..." section. Users are likely just scanning the headings and not reading the copy. It could be generally overwhelming and create too much cognitive load to some users and they may ignore the section.
**Feasibility Risks** (can we build it with available tech/data):
  - The idea of creating a “parallel” home page experience seems pretty straightforward but has not been tried before in recent memory. There are potential challenges to our ideas, including Analytics setup and Search API integration. Future CMS integration has not yet been explored for feasibility or level of effort.
  - Changes to the codebase are small and localized. The only external dependency relates to the Search component, but the implementation and functionality will be identical to the search that already exists in the header. 
**Organizational Viability Risks/Constraints** (will there be a positive organizational impact):
  - We may need the support of teams outside of OCTO-DE to get our experiment live on a va.gov subdomain.

## Prioritization

Given the strong evidence for change and experimental nature of our work, we intend to implement several ideas at once. Further refinement will be possible later, especially when any of these changes is moved to production.

<details>
<summary> First build - March 2022 </summary>
 
![First build design](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/public-websites/images/va-home-page-first-build.png)

</details>

### Summary of changes
 - A randomized, rotating set of Veteran portraits has been added to the top of the page (but will not appear in mobile experience) 
 - Sign in/Sign up CTA has elevated visibility and top placement
 - Four top task boxes have been replaced with a data-driven list of links to 5 Veteran-facing pages where actions can be taken 
 - A visible search option which mimics the site search is available, followed by a data-driven list of four other search tools not available through Search (such as Yellow Ribbon, Education benefits, Find a VA form, Facility Locator)
 - VAntage blog article appears in prominent location with requirements to be Veteran facing and refreshed weekly, at a minimum
 - Benefit hubs are listed based on use volume
 - Static row of Veteran images appear immediately above the footer
 - Governance and guidance is available to establish required content, character limitations and criteria for inclusion of links and tasks

**Value proposition**
- Veteran portraits humanize VA and remind stakeholders who VA.gov is intended to serve
- By using analytics to determine search tools and task lists, we can ensure optimal use of space
- Delivers simplified, easy to read design 

**Out of scope**
- Initial scope will not include the header and footer as these are shared across VA.gov and developing consensus on their use will be significantly more complicated. 
- The “Other VA resources” section (which contains links to other VA resources such as Choose VA, Resources and Support, VSO websites, VA offices and Programs) is found in the design but not implemented in the testing version as the links are not Veteran-facing. 

## Next steps

### Research
- Conduct Veteran research to identify top tasks, informing the list of "most popular" links which replace the 4 top task boxes in the new iteration
- Validate design changes with Veterans, including those who use screen readers, screen magnification, and voice command at a variety of experience/skill levels and a variety of devices, with the following goals
  - confirm list of "popular links" along with validating that Veterans understand to search for other tasks not appearing on that short list
  - understand Veteran expectations of search behavior
- Research findings should be shared broadly, including Authenticated Experience team and Apartment teams

### Connection to authenticated experience
- Explore routed queries - direct Veterans to a deep link rather than the search results page
- Determine expected behavior for logged in users
  - should sign in/sign up CTA still be present? 
  - user flow when My VA becomes the logged in home page (expected Summer 2022)
--- 

## Launch Planning
### Collaboration Cycle
> 💡 *Use for any Collab Cycle tracking, questions.*
- Epic: [VA.gov Home page redesign #40845](https://github.com/department-of-veterans-affairs/va.gov-team/issues/40845)
- Kickoff ticket
- Design intent [CMS-Offices team - VA.gov Home Page #39038](https://github.com/department-of-veterans-affairs/va.gov-team/issues/39038)
- Research [Epic: Veteran Top Task Research (moderated and unmoderated) #40857](https://github.com/department-of-veterans-affairs/va.gov-team/issues/39038)
- Research [Epic: Usability of redesigned home page #41578](https://github.com/department-of-veterans-affairs/va.gov-team/issues/39038)
- Analytics requests
  - [Search DOMO #41512](https://github.com/department-of-veterans-affairs/va.gov-team/issues/41512)
  - [Content DOMO #41503](https://github.com/department-of-veterans-affairs/va.gov-team/issues/41503)

### Go-to-market strategy
> *What marketing, outreach, or communications are necessary for this product to be successful? Which groups/orgs are necessary to make this happen?*

1. Deploy first build into publicly available interactive environment (for access by stakeholders and usability research)
2. Request analytics support
3. Develop usability research plan
4. Discussions with VA leadership, Digital media partners and other stakeholders
5. Evolution of Web Governance board

### Timeline 
> *Describe any major milestones for this initiative including organizational, legislative, etc. constraints.*

| Date | Milestone|
|---|---|
| March 39, 2022 | Design intent |
| June 3, 2022 | Moderated Top Task research synthesis - [findings](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/teams/vsa/teams/public-websites/research/Veteran-tasks/moderated/research-findings.md) |
| June 3, 2022 | First build deployed to staging |  
| June 2022 | Unmoderated Top Task research - _findings (TBD)_ |
| July 2022 | Usability research | 

#### Initiative Launch Dates
- *Target Launch Date*
  - tbd
- *Actual Launch Date* 
  - tbd

---
   
## Screenshots

### Before (Current)
<details>
<summary> VA.gov home page as of 3/1/2022 </summary>

![Current homepage](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/public-websites/images/va-home-page-current.png)
</details>

### After (Still on VA.gov subdomain)
<details>
<summary> First build - June 2022 </summary>
 
![First build design](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/products/public-websites/images/va-home-page-first-build.png)

</details>

---
<sup>1</sup> [VA.gov Analytics - KPI Framework](https://github.com/department-of-veterans-affairs/va.gov-team/blob/master/platform/analytics/Analytics%20Playbook/va-gov-platform-analytics-kpi-framework.pdf)\
<sup>2</sup> [SVPG: The Four Big Risks](https://svpg.com/four-big-risks/)


