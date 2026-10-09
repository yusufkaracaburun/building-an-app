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

**Test against a real server, not a fake one.**
In the beginning the app talked to a "mock": a fake server that we wrote ourselves, so we could build before the real server was ready. After a while the mock was out of date. It still sent an old field name, so our tests proved the app worked with our fake, not with the real thing.
From now on: once the real server runs on your own computer (a local test server), throw the mock away and test against that.

**End-to-end tests only check the main road.**
An end-to-end test (E2E) uses the app the way a person does, from start to finish. Those tests are slow. We first put error cases in them too, like "what if you type a date twice?", and that made them slower without catching more bugs.
From now on: the E2E test checks the happy flow (everything goes right). Error cases go in small, fast unit tests, which test one piece of code on its own.

**Prove that your test can fail.**
A test that always passes is useless. For the "book several days at once" feature we removed the safety code on purpose and checked that the test turned red. Only then did we trust the green result.
From now on: for important logic, break the code once on purpose and watch the test fail.

**Change a rule, run all the tests again.**
The server got a new rule: you may only book hours on activities measured in hours. Our E2E test set up its own test activity, but it picked a random unit. The new rule rejected it, and nobody noticed until we ran the test again.
From now on: after every rule change, run every test, also the slow ones.

**Never move things inside a master in the design file.**
In Pencil (our design tool), a "master" is a building block that many screens reuse, like a stamp. The designer moved one text inside the master of a list row. Every screen that had changed that row (for example its status label) lost its change, and we had to repair them all by hand.
From now on: change a master only by editing its look, never by moving nodes around inside it. Make a backup before a big change or cleanup.

**Grey means "you cannot tap this".**
In the date picker, some days were grey. Our test users would read grey as "switched off", while those days were fine to pick. We also showed hours in four different ways (7,5 and 7:30 and more).
From now on: only make something grey when it really is disabled, and show the same kind of value in one way everywhere.

**An app icon has a safe zone.**
iOS rounds the corners of an icon. Android cuts a shape out of it, often a circle, and every phone brand does it a bit differently. So the logo needs empty space around it, and on Android it needs more space than on iOS.
From now on: draw the icon with a safe zone and check it inside both the iOS shape and a round Android mask.

**Old passwords hide in your computer's settings.**
The GitHub command line kept failing with "can't log in". An old login key (a "token") was still saved in an environment variable: a setting that every new terminal copies. Removing it in one terminal did not help, because the next one copied it again.
From now on: if a login keeps failing, check for an old key in your settings file and remove it there.

**Commit small, and review before you commit.**
We saved our work in git in small steps: one commit per finished piece, each with green tests. Before each commit a review step checks the change for code that is not needed. A hook (a small script that runs by itself) blocks the commit if you skipped the review.
From now on: small commits, tests green, quick review, then commit.

## 2026-10-08 · The first app

**An independent judge gives the score.**
Every design gate (a checkpoint where the design has to be good enough before you go on) got a score out of 100. The score came from a reviewer who had not seen earlier rounds, never from the designer. The first login screen started at 67 and needed about nine rounds to reach 91.
From now on: set the bar (for us 90 out of 100) before you start, and let someone who did not make the design give the score.

**Say no to gimmicks, even if a reviewer asks for them.**
A reviewer said our design looked too ordinary. To get a higher score we added a tilted "CHOSEN" stamp on the selected row. The client found it childish: a different row colour and a small vibration already show what you picked.
From now on: show what is happening with plain means (colour, a check mark, a vibration). Do not add decoration just to make a design "special".

**Not every screen has to be drawn.**
We drew the same screen in several languages. Every copy looked the same, so it only cost time and made the design file messy.
From now on: only draw a variant if its layout is different. Check the rest in the real app.

**Do not pass on feedback without thinking.**
We forwarded the reviewer's fix list straight to the designer. That is how the gimmick stamp and the extra language screens got in. The client then had to catch them himself.
From now on: read every piece of feedback first and ask: is it childish, is it overkill, is it tidy, is it easy to maintain? Only pass on what survives.

**Measure it yourself.**
The designer reported that the language button was 48 points high, big enough to tap easily. When we measured the exported picture ourselves, it was 20.
From now on: check numbers yourself (sizes, contrast) instead of trusting the report.

**Small fixes cannot save a bad layout.**
The first login screen had a big empty area. We moved things around three times, but the empty space just moved to a different spot. Only after looking at real, well-designed apps did we choose a new direction, and then the score went up.
From now on: if two fix rounds do not help, stop patching. Look for good examples and start the layout again.

**Design for people who find apps hard.**
Our users are not used to apps. So every screen has one main button, as wide as the screen and at least 56 points high; everything you can tap is at least 48 points, text is at least 17 points, and labels sit above the input field. The app still had to look grown-up, not like a kids' app.
From now on: write these rules down before the first design and give them to every designer and reviewer.

**A poster is not an app screen.**
We designed the poster with the QR code in the same calm style as the app. It looked boring. A poster on a wall has to catch your eye from three metres away.
From now on: choose the style for the medium. Calm for a screen you use every day, bold for something that must stand out.

**Draw screens inside a phone frame.**
At first the screens were flat rectangles. With round corners like a real phone, a thin border and a status bar at the top, they suddenly felt like a real app. The client wanted this for every design from then on.
From now on: put the phone frame on the master screen once, so every screen gets it automatically.

**Unlock with a PIN code, keep it on the phone.**
Typing an email and password every time is annoying. So you log in once, and after that you unlock the app with a 4-digit PIN or your face or fingerprint; the PIN never leaves the phone and is stored mixed with a "salt" (extra random data) so nobody can read it back. After 5 wrong tries everything is wiped and you log in with your email again.
From now on: decide up front how many tries, when the app locks again, and what "forgot PIN" does.

**Several AI helpers, one file at a time.**
Several AI sessions shared one design app. During another session's turn, our design file was also open, and their work ended up saved in our file. We had clicked "Save" on a pop-up we did not expect.
From now on: say "busy" before you start and "free" when you are done. Keep only your own file open. If an unexpected "save changes?" pop-up appears, press Cancel and first check what changed.

**Ask before you add a new package.**
A package (dependency) is someone else's code that you add to your app. Every package can break, slow down or stop being maintained. We asked for approval for each new one, and skipped some: no QR scanner, because the phone camera can already read QR codes.
From now on: ask "can the phone or the code we have already do this?" before you add a package, and write down why you chose it.

**Let the server write the types.**
The server publishes a file that describes every request and answer (OpenAPI). From that file a tool creates "types" for the app: rules that say what each field looks like. When the server changes a field, the app no longer compiles, so you see the problem right away.
From now on: never type the server's types by hand. Generate them again after every server change.
