---
title: "How I Created This Website"
date: 2019-08-06
---

## Introduction

This is an overview of the steps I took to create this website with GitLab pages, Cloudflare and Hugo. It's not supposed to be a comprehensive step-by-step guide, but more of a checklist that you can follow if you want a similar website setup.

## Getting a domain

Getting your own custom domain is entirely optional for GitLab pages as you get a free subdomain at `your-username.gitlab.io`. It's however highly recommended that you get your own domain to prevent being locked to GitLab. Your own domain can easily be pointed to a different host if you want, but a subdomain at GitLab can never be seamlessly pointed elsewhere.

I decided to get a .se domain, the Swedish TLD (Top Level Domain). The Swedish TLD is not available at most common US registrars such as [Namecheap](https://namecheap.com), so I registered through a Swedish company. I chose [Binero](https://binero.se), not for any particular reason other than I have previous experience with them and they are one of the cheaper companies for .se. Any domain registrar should be fine, at least for .se domains where [WhoisGuard](https://namecheap.com/support/knowledgebase/article.aspx/278/37/what-is-whoisguard) is not needed as personal information is already hidden.

Make sure you use a registrar with WhoisGuard if you buy a different TLD with public personal information, such as .com.

## Creating a GitLab page

1. [Create a GitLab account](https://gitlab.com)
2. [Create a new project](https://gitlab.com/projects/new). Name it **username.gitlab.io** (replace username with your username).

Additional steps if you have a domain:

1. Go to the page settings for your project, available at `https://gitlab.com/username/username.gitlab.io/pages`.
2. Add your new domain.
3. Save the verification code shown. You'll need this in the next step.

## Configuring DNS with Cloudflare

Once you have your custom domain (you can skip this section if you decided not to get one), you need to point your domain to your GitLab page. You can either configure everything through your domain registrars control panel or use Cloudflare. My reasons to use Cloudflare is that their configuration interface is MUCH better than the one at Binero, more documentation is available/up-to-date, and they provide basic analytics. Analytics at Cloudflare is great because it show the amount of visitors and from what countries they come from, all without adding any JavaScript spyware to your website, like Google Analytics.

To get started with Cloudflare, [create an account](https://dash.cloudflare.com/sign-up), add your domain and follow the steps. One of the steps is setting the domain's nameservers to those of Cloudflare. Setting the nameservers is done through your domain registrars control panel.

Once your nameservers have been set and Cloudflare have detected them, you can start configuring the DNS. Go to your site's dashboard and press the DNS tab.

This is what my records looks like. Replace with your own domain and the verification code you saved from the GitLab page step above.

Type    | Name                              | Value
------- | --------------------------------- | ---
`A`     | `limero.se`                       | `35.185.44.232`
`CNAME` | `www`                             | `limero.se`
`TXT`   | `_gitlab-pages-verification-code` | `gitlab-pages-verification-code=abc`

### Additional configuration

These steps are optional, but recommended.

1. On the "Crypto" tab in the dashboard. Set `SSL` to `Full` and enable `Always Use HTTPS`.
2. [Add Origin Certificate from Cloudflare to GitLab](https://about.gitlab.com/2017/02/07/setting-up-gitlab-pages-with-cloudflare-certificates)
3. [Redirect www.domain.com to domain.com](https://docs.gitlab.com/ee/user/project/pages/custom_domains_ssl_tls_certification/#redirecting-wwwdomaincom-to-domaincom-with-cloudflare). The `CNAME` will already be set if you copied my records, so you only need to add a Page Rule.

## Hugo static website generator

[Hugo](https://gohugo.io) is used to generate this website. All these blog posts are written in Markdown and then converted. When using Hugo, you'll need to pick a theme. Go through the list at [Hugo Themes](https://themes.gohugo.io) and pick one that you like. I picked [Lithium](https://themes.gohugo.io/hugo-lithium-theme) and then configured it to my liking.

1. Start by following the official [Quick Start Guide](https://gohugo.io/getting-started/quick-start).
2. Add your files to the GitLab page repository you created in a previous step.
3. Create a file in the root of the project called `.gitlab-ci.yml` and add the content from [here](https://gitlab.com/Limero/limero.gitlab.io/blob/master/.gitlab-ci.yml).
4. Commit everything and GitLab should automatically build your site.

You should now be able to visit and see your website at your domain and the subdomain at `your-username.gitlab.io`. Don't panic if your domain doesn't work right away, it might take a few hours for everything to be updated.
