# readlater

A small, manually invoked [GitLab](https://about.gitlab.com/) CI/CD pipeline that will accept a URL variable (`SITE_TO_READ_LATER`) and then download that page, package it as a `.mobi` ebook and then send it to your Kindle.

[Write up](https://az.id.au/ops/read-later/) for this project.

## Setup

You'll need to set the following variables in the GitLab CI interface:

* MSMTPSERV - Your mail server/MTA.
* MSMTPFROM - The "from" component of your SMTP sign on.
* MSMTPUSER - The username for your SMTP login.
* MSMTPPASS - The password for your SMTP login.
* KINDLEEMAIL - Your personal Kindle document email.

## Send-To-Kindle Enable

You'll have to log into your Amazon account, go to Content And Devices, go to Preferences, and find the section about sending to your Kindle via email and add your email address as a verified sender. This is a setting to prevent people spamming your Kindle with viagra ebooks. I'm happy to send you viagra ebooks if you want though. Or PDFs with cheap rolexes.

## Security Considerations

Anyone with sufficient privileges on your GitLab repository/instance may be able to view these variables, which does include a password so please be cautious.

Also note anyone with sufficient privilege may be able to run pipelines, so lock that down too.