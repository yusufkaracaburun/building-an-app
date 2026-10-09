# Lessons

Each lesson: what happened, what we learned, what we do from now on.
Newest on top.

## 2026-10-09 · The first app

**A new operating system can break your app.**
On iOS 27 the app crashed the moment it started. Since that version Apple requires a different way of starting an app, and our version of Expo did not do that yet. On an older iPhone simulator everything worked, so without testing on the newest version we would only have found out from users.
From now on: always test on the newest iOS and Android, and on the newest phones.

**The same words everywhere.**
A status was called one thing on the website and another thing in the app. The server knew eight statuses, the app only five.
From now on: one list of words in one place (the "glossary"), and a test that checks the apps follow that list.

**Choose the folder structure once.**
An app grows. If the folders are wrong, you later have to move hundreds of files.
From now on: choose up front, write it down in an ADR, and let a test check that everyone sticks to it.

**Ask the data, not your gut feeling.**
We wanted to guess how people book their hours. The real data showed that most people book several days at once. That made "Monday to Friday in one go" a main feature.
From now on: first look at what users really do.

**Design first, then build.**
The first version of the "book hours" screen was too complicated. We saw that in the design, and redesigning took a few hours. In code it would have taken days.
From now on: no code before the design is approved.

**Look for yourself, do not just trust the report.**
The designer reported that the Q in the icon was right, but the inside of the Q was filled in. We only saw it by looking at the picture ourselves.
From now on: look at every result yourself before it is approved.

**Tests make their own test user.**
A test that needs a real user fails as soon as someone changes that user, and it can damage real data.
From now on: the test creates its own user and cleans everything up afterwards.

**Not every tool fits every app.**
Patrol is a testing tool for Flutter apps. Our app is React Native, so we chose Maestro.
From now on: first check whether a tool fits your technology.
