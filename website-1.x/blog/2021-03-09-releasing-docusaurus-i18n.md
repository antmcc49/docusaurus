---
title: Releasing Docusaurus i18n
author: Sébastien Lorber
authorTitle: Docusaurus maintainer
authorURL: https://sebastienlorber.com
authorImageURL: https://github.com/slorber.png
authorTwitter: sebastienlorber
tags: [release, i18n]
image: /img/blog/2021-03-09-releasing-docusaurus-i18n/social-card.png
---

Today, we officially release **[Docusaurus 2 i18n](https://v2.docusaurus.io/docs/i18n/introduction)**, as part of [2.0.0-alpha.71](https://github.com/facebook/docusaurus/releases/tag/v2.0.0-alpha.71).

In this post, we will present you the **translation workflow**, explain some **design decisions** and **showcase early adopter sites**: [Jest](https://jestjs.io/), [Redwood](https://learn.redwoodjs.com/), and [Datagit](https://datagit.ir/).

With i18n, Docusaurus 2 has reached **full feature parity with Docusaurus 1**, and a first **2.0 beta** is on its way.

We believe that **we went the extra mile**, and the i18n support in Docusaurus 2 is **even better than in Docusaurus 1**.

## Translate your site

You can translate a Docusaurus site in **3 simple steps**:

- **Configure**: declare the default locale and alternative locales in `docusaurus.config.js`.
- **Translate**: put the translation files at the correct file-system location.
- **Deploy**: build and deploy your site using a single or multi-domain strategy.

The [i18n tutorial](https://v2.docusaurus.io/docs/i18n/tutorial) is the best way to get started.

The i18n support is **flexible** and based on the **file-system**. We provide help to use **[Git](https://v2.docusaurus.io/docs/i18n/git)** and **[Crowdin](https://v2.docusaurus.io/docs/i18n/crowdin)**.

## Design decisions

The goals of the Docusaurus i18n system are:

- **Simple**: just put the translated files in the correct file-system location.
- **Flexible translation workflows**: based on Git (monorepo, forks, or submodules), SaaS software, FTP...
- **Flexible deployment options**: single, multiple domains, or hybrid.
- **Modular**: allow plugin authors to provide i18n support.
- **Low-overhead runtime**: documentation is mostly static and does not require a heavy JS library or polyfills.
- **Acceptable build-times**: allow building and deploying localized sites independently.
- **Localize assets**: an image of your site might contain text that should be translated.
- **No coupling**: not forced to use any SaaS, yet the integration is possible.
- **Easy to use with [Crowdin](http://crowdin.com/)**: multiple Docusaurus 1 sites use Crowdin, and should be able to migrate to v2.
- **Good SEO defaults**: setting useful SEO headers like [`hreflang`](https://developers.google.com/search/docs/advanced/crawling/localized-versions) for you.
- **RTL support**: locales reading right-to-left (Arabic, Hebrew...) should be easy to use.
- **Default translations**: theme labels are translated for you in [many languages](https://github.com/facebook/docusaurus/tree/master/packages/docusaurus-theme-classic/codeTranslations).

## Showcase

We worked with a few volunteers to **dogfood the i18n support** before releasing it.

### Jest: upgrading Docusaurus

An **existing Docusaurus 1 site** using i18n should be **able to upgrade to Docusaurus 2** and still be translated.

**[Jest](https://jestjs.io)** was one of those sites, and we [**successfully upgraded it to Docusaurus 2**](https://jestjs.io/blog/2021/03/09/jest-website-upgrade).

[![Jest i18n screenshot](/img/blog/2021-03-09-releasing-docusaurus-i18n/jest.png)](https://jestjs.io)

### Redwood: adopting Docusaurus

[Redwood](https://redwoodjs.com/) is a React full-stack Jamstack framework.

They were looking for a solution to create an **internationalized learning platform**, and became early adopters of Docusaurus 2 i18n for [learn.redwoodjs.com](https://learn.redwoodjs.com/), using Crowdin to get it translated to French.

[![Redwood i18n screenshot](/img/blog/2021-03-09-releasing-docusaurus-i18n/redwood.png)](https://learn.redwoodjs.com/)

### Datagit: using Docusaurus LTR support

The i18n system should work with any language, including **Right-to-Left languages**.

[Datagit.ir](https://datagit.ir/) is using Farsi, and a simple configuration option is able to **flip the Docusaurus theme** to add the required Right-to-Left support.

[![Datagit i18n screenshot](/img/blog/2021-03-09-releasing-docusaurus-i18n/datagit.png)](https://datagit.ir/)

## Conclusion

We sincerely hope you will adopt and like the new i18n support.

This feature has not been an easy one, and we would like to thank everyone that got involved in this journey:

- [Alexey](https://github.com/lex111) for his help to make the i18n support exhaustive and even better than v1.
- [Simen](https://github.com/SimenB) for volunteering and supporting the Jest migration.
- [Claire](https://github.com/clairefro) for adopting Docusaurus 2 on the new Redwood platform and providing many feedbacks.
- [Massoud](https://github.com/massoudmaboudi) for reviewing my work on LTR and adopting it on Datagit.
- The [Crowdin](http://crowdin.com/) team for their support and willingness to improve their translation SaaS for our specific use-cases.
- The whole Docusaurus community for their patience, and providing many useful feedbacks on Github issues.

Thanks for reading.

🙏 And please, add your brand new i18n sites to our [showcase page](https://v2.docusaurus.io/showcase). We accept any Docusaurus site here, and we are working on a [redesign](https://github.com/facebook/docusaurus/issues/4238) allowing you to filter sites by features.