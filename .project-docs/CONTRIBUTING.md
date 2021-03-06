Contributing to fedora-happiness-packets
========================================

These guidelines explain how to submit changes to [fedora-happiness-packets](https://pagure.io/fedora-commops/fedora-happiness-packets).
Following these guidelines help maintainers review new pull requests.
Not following these guidelines may make it harder or take longer to review your change.
If you have questions about any of these guidelines, please ask in the [Community Operations team channels](https://docs.fedoraproject.org/en-US/commops/#find-commops).


## Goals

Our goals are the purpose of our development.
All changes should align to project goals.
This helps focus our development efforts and be a considerate downstream (a.k.a. forked) project.
Changes that do not align to these goals may not be accepted by maintainers.

More goals may be added to this list in the future.

### 1. fedora-happiness-packets is a fork.

[fedora-happiness-packets](https://pagure.io/fedora-commops/fedora-happiness-packets) is a fork of [mxsasha/happinesspackets](https://github.com/mxsasha/happinesspackets).
The upstream project is also active and in use.
As a considerate downstream, if a change could also help upstream, we should direct changes there.
Any changes directed to upstream should be [good pull requests](https://medium.com/@hugooodias/the-anatomy-of-a-perfect-pull-request-567382bb6067).
A positive relationship with our upstream project is important.

### 2. fedora-happiness-packets supports changes required for deployment in Fedora community.

Changes to fedora-happiness-packets should generally be Fedora-specific.
This could include [fedora-messaging](https://fedora-messaging.readthedocs.io/) support, Fedora-related design changes, or integrating into other parts of the Fedora community.
Sometimes there may be exceptions.
When deciding exceptions, always consider Goal 1.

### 3. Good code is tested code.

Introducing new code means introducing new tests.
If writing code that could be tested, it is code that should be tested.
This will be considered for introducing new functionality or unique code to fedora-happiness-packets.


## Create a development environment

Coming soon. Pending other open pull requests.


## Start working on a ticket

Want to work on a new ticket?
Follow these three steps:

1. Check if ticket has [![PASSED](/fedora-commops/fedora-happiness-packets/issue/raw/files/d4820df9449fd61951d807b5fe86231092a31db15932759b2b7b810262c002d0-Screenshot_2019-02-24_Settings_-_fedora-commops_fedora-happiness-packets_-_Pagure_io.png)](/fedora-commops/fedora-happiness-packets/issue/raw/files/d4820df9449fd61951d807b5fe86231092a31db15932759b2b7b810262c002d0-Screenshot_2019-02-24_Settings_-_fedora-commops_fedora-happiness-packets_-_Pagure_io.png "PASSED") label
2. Check if ticket is already assigned
3. Leave a comment in the ticket to work on it

Issues with the [![PASSED](/fedora-commops/fedora-happiness-packets/issue/raw/files/d4820df9449fd61951d807b5fe86231092a31db15932759b2b7b810262c002d0-Screenshot_2019-02-24_Settings_-_fedora-commops_fedora-happiness-packets_-_Pagure_io.png)](/fedora-commops/fedora-happiness-packets/issue/raw/files/d4820df9449fd61951d807b5fe86231092a31db15932759b2b7b810262c002d0-Screenshot_2019-02-24_Settings_-_fedora-commops_fedora-happiness-packets_-_Pagure_io.png "PASSED") label passed maintainer review.
This means they are accepted as tasks to work on.
Working on a ticket without the [![PASSED](/fedora-commops/fedora-happiness-packets/issue/raw/files/d4820df9449fd61951d807b5fe86231092a31db15932759b2b7b810262c002d0-Screenshot_2019-02-24_Settings_-_fedora-commops_fedora-happiness-packets_-_Pagure_io.png)](/fedora-commops/fedora-happiness-packets/issue/raw/files/d4820df9449fd61951d807b5fe86231092a31db15932759b2b7b810262c002d0-Screenshot_2019-02-24_Settings_-_fedora-commops_fedora-happiness-packets_-_Pagure_io.png "PASSED") label means your work may not be accepted.

If someone else is already assigned, it means the task is **already in progress**.
An assigned ticket is not available to start new work.
If a ticket has no updates for longer than seven days, you may follow up and ask if the assignee is still working on the ticket.

Finally, **leave a comment** in the ticket you want to work on.
A maintainer will reply asking for more information or they will assign the ticket to you.
When you are assigned a ticket, this means you are approved to work on it.


## Submit a pull request

These guidelines help maintainers review new pull requests.
Stick to the guidelines for quicker and easier pull request reviews.

1. Prefer gradual small changes than sudden big changes
2. Write a helpful title for your pull request (if someone reads only one sentence, will they understand your change?)
3. Address the following questions in your pull request:
    1. What is a summary of your change?
    2. Why is this change helpful?
    3. Any specific details to consider?
    4. What do you think is the outcome of this change?
4. Include screenshots of before/after if your change is a front-end change.
