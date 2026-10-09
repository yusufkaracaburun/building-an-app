# Glossary

Every word in this repo that you might not know, explained in one or two sentences.
If you find a word that is not here, add it.

## Apps and code

- **App**: a program on your phone. You tap it, it does something for you.
- **Code**: the instructions a computer follows, written in a language the computer understands.
- **Programming language**: a language for writing code. We use **TypeScript**, a version of JavaScript that checks your work while you type.
- **React Native**: a way to write one app in TypeScript that runs on both iPhone and Android.
- **Expo**: a set of tools on top of React Native that makes building, testing and publishing easier.
- **Package** (or dependency): code someone else wrote that you add to your app, so you do not have to write it yourself.
- **Bug**: a mistake in the code that makes the app do the wrong thing.

## Phones and testing

- **iOS / Android**: the two operating systems for phones. iOS is on iPhones, Android on most other phones.
- **Simulator / emulator**: a fake phone on your computer, so you can try the app without a real phone.
- **Test**: a small piece of code that checks other code. If the check fails, the test turns red.
- **Unit test**: a test for one small piece of code on its own. Fast.
- **E2E test** (end-to-end): a test that uses the whole app like a person would, from start to finish. Slow, but close to real life.
- **Happy flow**: the path where everything goes right.
- **Lint**: a tool that reads your code and warns about mistakes and messy style.
- **Type check**: TypeScript checking that every value is the kind of thing you said it would be.

## Servers and data

- **Server**: a computer somewhere else that stores data and answers questions from the app.
- **API**: the agreed way the app asks the server something and gets an answer back.
- **Contract**: the written list of what the app may ask and what the server answers.
- **OpenAPI**: a standard file format for writing down that contract.
- **Database**: where the server keeps its data, like a very big, very fast spreadsheet.
- **Mock**: a fake server you write yourself, so you can build before the real one is ready.
- **Token / key**: a secret code that proves who you are. Never put it in your app or in a public repo.

## Working together

- **Git**: a tool that remembers every version of your files, so you can always go back.
- **Commit**: one saved step in git, with a short message about what changed and why.
- **Repository** (repo): a project folder that git keeps track of.
- **GitHub**: a website where you store a repo online and work on it with others.
- **Review**: someone else (or a tool) reads your change before it is saved for good.

## Design and planning

- **MVP** (minimum viable product): the smallest first version that is already useful.
- **Design file**: a drawing of every screen before you build it. We use a tool called Pencil.
- **Master**: a building block in the design file that many screens reuse, like a stamp.
- **Gate**: a checkpoint. You only move on when the work is good enough.
- **ADR** (architecture decision record): a short note that writes down a big decision and why you made it.

## AI

- **AI** (artificial intelligence): a computer program that has learned from lots of examples and can write text, answer questions or write code.
- **Claude**: the AI we work with, made by a company called Anthropic.
- **Claude Code**: Claude working in your project folder. It can read your files, write code and run commands, but it asks before risky steps.
- **Prompt**: what you type to the AI. A clear prompt gets a better answer.
- **Claude API**: a way for your own app or script to talk to Claude. It needs a key, and that key must stay secret on a server.
