# Building an app, from idea to app store

This is the route we are walking with the first app, a time-tracking app for companies. Later we walk the same route with your own app.
Each phase has a goal, steps, tools and a gate: you only move on when the gate is open.

Status: we have done phases 1 to 6, phase 7 is in progress, phases 8 and 9 are still ahead. What is written there is the plan, not experience yet.

## 1. Idea

Goal: know who the app is for and which problem it solves.

- Write it down in two sentences: who uses it, and what becomes easier?
- Look at how people do it today. In the first app: employees wrote their hours on paper, or in a web app at the office.
- Choose what goes into the first version (the MVP, "minimum viable product"). Everything else goes on a "later" list.

Gate: you can explain the app in one sentence to someone who knows nothing about it.

## 2. Ask questions before you build

Goal: find the unclear choices before they cost time or money.

- Let someone question you: what happens when something goes wrong? Who is allowed to do what? What if there is no internet?
- Do you have real data? Use it instead of guessing. In the first app we chose the default value and the quick picks based on what users really book.
- Write down every decision, with the reason.

Gate: every question has an answer, or is on the "later" list on purpose.

## 3. Design, screen by screen

Goal: see what the app looks like before you write code. Changing a design is cheap, changing code is expensive.

- Tool: Pencil (design file `.pen`).
- First the building blocks: colours, fonts, buttons. Then per screen: every state (empty, loading, error, done), in light and dark mode.
- Every screen inside a phone frame, so it looks real.
- A second pair of eyes gives a score. Below 90: improve it.

Gate: the client (for you: yourself, or your customer) approves the design.

## 4. Agreements with the server (API)

Goal: the app and the server speak the same language.

- Write down which data the app asks for and what it gets back (the "contract").
- Let the server publish the contract (OpenAPI), and let the app generate its types from it. Then you notice a change straight away.
- One word per idea, the same everywhere. In the first app, statuses lived in three places with three different words.

Gate: the app can fetch real data from a test server.

## 5. Build in small pieces, test first

Goal: working code, step by step.

- Tools: Expo (React Native), TypeScript, Jest for tests.
- Work in small pieces ("slices"). First a test that fails, then the code that makes it pass.
- Agree on the folder structure once and write it down (an ADR, "architecture decision record"). After that, new code always goes in the agreed place.
- Every step: lint, type check and tests green, and only then save it in git.

Gate: all tests green, and the screen looks like the design.

## 6. Test on real devices

Goal: know it works where users use it.

- Tool: Maestro, a test that operates the app like a person (tap, type, look).
- Test on the newest iOS and Android, and on the newest phone models.
- A test creates its own test user and cleans everything up afterwards.

Gate: the test passes twice in a row, on both platforms.

## 7. Icon and splash screen

Goal: you recognise the app straight away on the home screen.

- Draw the icon as a vector, not as a picture.
- Mind the safe zone: iOS rounds the corners, Android cuts out a circle.
- Look at it at real size between other apps, also in dark mode.

Gate: approved and visible on both devices.

## 8. Getting ready for the store (still to do)

Plan: a unique app name (bundle id, for example `com.yourname.app`), screenshots, a privacy statement, a description, developer accounts with Apple and Google.

## 9. Publishing and after (still to do)

Plan: build with EAS, test with a small group first (TestFlight, Google's internal testing), then publish. After that, listen to users and pick up the "later" list.
