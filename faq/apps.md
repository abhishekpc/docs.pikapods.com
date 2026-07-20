---
title: Apps & Updates
nav_order: 2
layout: page
parent: FAQ
description: "Questions about app support, file editing, adding new apps and update policies."
---
# Apps & Updates
{: .no_toc }
1. TOC
{:toc}

## Support for Individual Apps
If you have any concerns with your PikaPods account, billing, or an offline pod, email [hello@pikapods.com](mailto:hello@pikapods.com) any time. You will generally receive a response within a few hours on working days.

Beyond this, we can't offer support for individual apps or their features. This is because they are developed, maintained, and distributed by independent third-party authors and communities. Our focus is on ensuring your hosting environment runs smoothly and we only charge for the resources to host these apps and don't monetize your data or charge for premium features. If you need additional support, see those options:

- **App Notes**: Many apps have [notes](/apps) that explain setup steps or common issues. You also find them via *See FAQ* in your pod control panel.
- **Project Documentation**: Visit the *Project Page* link of an app and read their documentation.
- **Env Var Documentation**: When setting up *Env Vars*, you will find a link to the official documentation explaining each setting.
- **AI**: Try asking your AI agent (e.g. ChatGPT or Claude) to look at the screenshot or error logs. Instruct them to look for known issues, confirm the issue in the source code or provide the SQL to debug in the database.
- **Community Forum or Chat**: There may be a forum or chat room for the app to ask questions and get help from other users.
- **Commercial Support**: Sometimes the author will offer commercial support. This is also a great way to support the app's development.
- **Github Issue**: If you think there is a bug in the app or you have an idea for a new feature, you can raise it with the developers on their GitHub Issues page.
- **Freelancer**: For more complex projects, it can make sense to get a professional. Freelancer sites like [Upwork](https://www.upwork.com/) are good places to find expert sysadmins or web designers. This works even for smaller tasks.


## Editing app files or source code
At *PikaPods* we deploy all apps as isolated containers. This means all dependencies and source code files are bundled by the app author and distributed as a container image. This means you get the same experience as running the same image directly and can be sure there are no modifications to the app.

Compared to other ways of deploying apps (like putting PHP files on shared hosting space), it's not recommended to make adjustments to any files that aren't explicitly mounted from the image and visible via SFTP. While it may work temporarily, all such changes will be lost during the next update or edit.

In the large majority of cases, you will find that all necessary files are available via SFTP and no further changes are necessary. If you think a new mounted folder should be made available for an app, do get in [touch](mailto:hello@pikapods.com) and it will be reviewed.


## Adding new apps
New apps are regularly being added. If your favorite app isn't available yet, you can suggest or vote for it on our [feedback](https://feedback.pikapods.com/) page. For an app to be suitable for PikaPods, it should roughly match those criteria:

- Be a web application and use one HTTPS port only
- Not use large amounts of CPU or bandwidth by design (e.g. video encoding)
- Not have a potential for abuse or impact on other pods (e.g. proxies or VPNs)
- Have a license that allows self-hosting
- Not compete with the author's own paid hosting service, unless alternative hosting options are actively promoted.
- Have an official (or semi-official) Docker image available
- Be actively developed and security issues are addressed


## Updating apps

Providing a stable experience is our top priority, so we don't roll out updates the moment they're released. Instead:

**Routine updates**
- We test each update in a staging environment before making it available to pods.
- Updates must be a stable release (as defined by the project) and have been available for at least 48 hours.
- These usually reach your pod within about a week of release, often sooner.
- If an update includes breaking changes (as defined in the release notes) that may require your attention, we'll email you one week beforehand.

**Security & urgent bug fixes**
- We apply these ad-hoc, as soon as the bugfix release is available.
- The update typically lands within a few hours.

Want to know when your pod updates? Enable notifications under *Edit Pod Settings > Basics > Notify me of updates*.


## Missing environment variables
When adding new apps, we will add the most common and useful env vars from the start. Sometimes this doesn't include very specific or newly added env vars. If you find that an env var you want to use is missing, just send us an email to [hello@pikapods.com](mailto:hello@pikapods.com) and we will add it right away.

## Disk Usage and Database Storage
Some apps primarily store their data in a database rather than using disk storage. For these apps, the disk usage bar will not be visible in the dashboard, and adding disk storage is not necessary. Examples include apps like Umami Analytics that primarily use database storage.

For database-intensive apps, we automatically allocate sufficient database storage space. Database storage does not count towards your disk usage quota and is provided free of charge.
