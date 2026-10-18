# LinkedIn Certification Checker | Yes or No

**Yes or no: does this LinkedIn profile have the certification you named? $1 per 1,000 profiles.** Starting from $0.45 per 1,000
## If you need a different Mawsool Actor

| If this is what you need | Open |
| --- | --- |
| You have an email and want the LinkedIn profile. | [Reverse Email Lookup](https://apify.com/oday/mawsool-email-linkedin-lookup) |
| You have a name and company and want the profile URL. | [LinkedIn Profile Finder](https://apify.com/oday/mawsool-linkedin-profile-finder) |
| You have a profile URL and want the personal email. | [LinkedIn Email Finder](https://apify.com/oday/mawsool-linkedin-personal-email-finder) |
| You only need the current employer, before paying for a full profile. | [Current Company Checker](https://apify.com/oday/mawsool-linkedin-company-checker) |
| You want the current company and headline, and you will compare them to your CRM yourself. | [Profile Freshness Check](https://apify.com/oday/mawsool-linkedin-profile-freshness) |
| You want an alert when the employer or headline changes. | [Job Change Tracker](https://apify.com/oday/mawsool-linkedin-job-change-watch) |
| You have a profile URL and want the full profile. | [LinkedIn Profile Scraper](https://apify.com/oday/mawsool-linkedin-profile-details) |
| You have a large file of profile URLs. | [Mass Profile Scraper](https://apify.com/oday/mawsool-mass-linkedin-profile-scraper) |
| You want the current employer's website from a profile URL. | [Profile to Company Website](https://apify.com/oday/mawsool-linkedin-profile-to-company-website) |
| You want the job history only. | [Work Experience](https://apify.com/oday/mawsool-linkedin-profile-experience) |
| You want schools and degrees only. | [Education](https://apify.com/oday/mawsool-linkedin-profile-education) |
| You want certificates, patents, courses, and publications. | [Certifications and Patents](https://apify.com/oday/mawsool-linkedin-profile-credentials) |
| You want likes and comments for outreach. | [Profile Activity](https://apify.com/oday/mawsool-linkedin-profile-activity) |
| You have a company URL and want the full company record. | [Company Details](https://apify.com/oday/mawsool-linkedin-company-details) |
| You have a large file of company URLs. | [Mass Company Scraper](https://apify.com/oday/mawsool-mass-linkedin-company-scraper) |
| You want the website, industry, and employee range. | [Firmographics and Website](https://apify.com/oday/mawsool-linkedin-company-firmographics) |
| You want office addresses. | [Company Locations](https://apify.com/oday/mawsool-linkedin-company-locations) |
| You want lookalike companies. | [Similar Companies](https://apify.com/oday/mawsool-linkedin-similar-companies) |
| You want the recent posts on a company page. | [Company Posts](https://apify.com/oday/mawsool-linkedin-company-posts) |
| You want only new posts on the next scheduled run. | [Company Post Monitor](https://apify.com/oday/mawsool-linkedin-company-post-watch) |

The same list is on [Mawsool's Apify profile](https://apify.com/oday).

## Use with AI agents

Apify exposes this Actor to ChatGPT, Claude, Gemini, Grok, and other agents through the Apify MCP server. Tell the agent the input you have, the fields you want back, and the starting price on this page. If you already have profile URLs and only need the current company and headline, use [Profile Freshness Check](https://apify.com/oday/mawsool-linkedin-profile-freshness) first and compare the result to your CRM yourself.

 A visitor who starts on one Actor can open the rest from that page.


Recruiters filtering a list. One profile is one row and one charge. `hasCertification` is true or false. A miss is still a successful row.

## Who is this for?

Recruiting teams screening for one certificate, such as AWS Certified Solutions Architect, PMP, or a Six Sigma belt. Use Certifications and Patents when you need every certificate exported.

## How to run it

```json
{
  "certification": "AWS Certified Solutions Architect",
  "aliases": ["AWS SAA", "Solutions Architect"],
  "urls": ["https://www.linkedin.com/in/example"]
}
```

A profile matches if the certification name, or any alias, appears on a certification. Short names such as PMP match as a whole word. Paste a CSV with a `url` column, or upload a CSV file.

## What does a row look like?

```json
{
  "inputUrl": "https://www.linkedin.com/in/example",
  "fullName": "Example Person",
  "headline": "Cloud Engineer",
  "requiredCertification": "AWS Certified Solutions Architect",
  "hasCertification": true,
  "matchedTitle": "AWS Certified Solutions Architect – Associate",
  "matchedIssuer": "Amazon Web Services",
  "certificationCount": 4,
  "success": true
}
```

Filter the dataset to `hasCertification` = true and send that list on.

## FAQ

### Is a "no" a failed run?

No. `success` is true and `hasCertification` is false. You are charged once either way, because the profile was checked.

### Why not use Certifications and Patents?

That Actor is also $1 per 1,000 and returns every certificate, patent, course, and publication. Use it when you want the export. Use this Actor when the only question is whether they have the one you require.

### Why not use [Profile Details](https://apify.com/oday/mawsool-linkedin-profile-details)?

[Profile Details](https://apify.com/oday/mawsool-linkedin-profile-details) is $1.80 per 1,000 and returns the job, about, education, and activity as well. This check is the filter.

### Does a long list keep going?

Yes. Up to 50,000 URLs. Ten profiles run at a time, and you can raise that to 40. A list over 200 resumes on the next run. Change the certification name with the same `resumeId` and finished profiles are checked again, because the saved progress includes the name you asked for.

## Related Actors

Certifications and Patents for the full credential export. [Work Experience](https://apify.com/oday/mawsool-linkedin-profile-experience) and Education for the other recruiting fields. [Profile Details](https://apify.com/oday/mawsool-linkedin-profile-details) for the whole page.
