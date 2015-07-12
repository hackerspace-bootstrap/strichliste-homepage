+++
date = "2015-07-11T20:23:21+02:00"
draft = false
title = "What is this project about?"
[menu]
  [menu.main]
    parent = "About"
+++

<quote>
_strichliste_ ([ʃtʀɪçˈlɪstə], German word for tally sheet) is a tool to replace
a tally sheet inside a hackerspace. It is the first project developed by the
[hackerspace bootstrap](https://github.com/hackerspace-bootstrap) organization.

It's aim is to provide a no-frills, easy-to-setup and -to-use solution for
managing your organization's snack bar.
</quote>

### Demo

That's what you're here for, right? You can access a demo of strichliste
[here](https://demo.strichliste.org/). But, just to be sure, here's how
it looks like:

![A screenshot of strichliste in action](/img/screenshot-main.png)

### Architecture

strichliste consists of two components: the `frontend` and the `backend`.

The frontend (`strichliste-web` on Github) is an angular-js based static web
application that accesses the backend via a RESTful HTTP interface.

The backend (`strichliste` on Github) is written in Javascript and runs in
nodejs. It is governed by a testsuite. All data is stored in a SQLite database
which supports deployment and simplifies backups.

### How it works

The processes implemented by strichliste inherently assumes to be used by a
trusted audience. Each user intending to buy something from your kiosk is
required to have a user account with strichliste. This can be done by
registering your username (no other data is required).

Once an account is available, buying an item is as simple as deducting the
equivalent value of the item from your account. Administrators of strichliste
can define a lower or upper bound for the users' credit balance. For example,
administrators can configure that it is not allowed to have a negative balance.

Cashing your account works the same as the inverse of buying an item: Simply
charge your account with the given amount and it will take effect immediately.

It's as simple as that!

### Troubleshooting

In case of problems, please file an issue on our Github issue tracker.
