
# Meritum News Mobile App
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54) ![JavaScript](https://img.shields.io/badge/javascript-%23323330.svg?style=for-the-badge&logo=javascript&logoColor=%23F7DF1E) ![Flutter](https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white) ![Firebase](https://img.shields.io/badge/firebase-a08021?style=for-the-badge&logo=firebase&logoColor=ffcd34) ![Supabase](https://img.shields.io/badge/Supabase-3ECF8E?style=for-the-badge&logo=supabase&logoColor=white) ![AWS](https://img.shields.io/badge/AWS-%23FF9900.svg?style=for-the-badge&logo=amazon-aws&logoColor=white) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white) ![CSS3](https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white)

A mobile app that presents the latest news from various sources in an objective and transparent manner. Created for mobile users looking for quick and easy access to current information without bias. Currently supporting Polish and English sources.

## About this repository

For safety reasons, I don't want to publish the entire application code, but I would be happy to explain how it works. The first thing worth mentioning is that it all started as a small summer project that eventually grew into a fully-fledged mobile app. I'm working on the entire project by myself while also balancing my studies, so I kindly ask for your understanding.

## Application Overview

The core of the application consists of web scrapers written in Python, automated using [`Playwright`](https://github.com/microsoft/playwright) for more secure and complex sites. These scrapers monitor reliable and credible news sources. Whenever new articles are published, they are scraped, summarized, and added to the [`Supabase Vector`](https://github.com/supabase/vecs) database. Once added to the database, a semantic similarity search is performed to find potential articles on similar topics. Using an LLM, the articles are verified for relevance and then rewritten into an unbiased summary, which is then stored in [`Firebase Firestore`](https://firebase.google.com/products/firestore) for easy access by the frontend. The scrapers are hosted on [`AWS Lambda`](https://aws.amazon.com/lambda) and are triggered at set intervals.

The frontend was primarily built using the low-code tool [`FlutterFlow`](https://www.flutterflow.io/product), but due to its limitations, it served as a base for further manual code modifications, enhanced with custom scripts and widgets. The entire graphic design of the project was created by me (definitely the hardest part of the project).

## Tech Stack

- **Frontend**: 
  - `Flutter`

- **Backend**: 
  - `Python` (with many libraries including [`playwright`](https://github.com/microsoft/playwright), [`requests`](https://github.com/psf/requests), [`vecs`](https://github.com/supabase/vecs))
  - Really basic `JavaScript` for edge functions in databases

- **Frameworks**: 
  - Unfortunately, none due to the unforeseen growth of the project and lack of time to rewrite it from scratch

- **Databases**: 
  - `Firebase Firestore`
  - `Supabase Vector`

- **Hosting**: 
  - `AWS Lambda`

- **Website (required by app stores)**: 
  - Simple `HTML` and `CSS`

## Download

You can download and test the app on Android/iOS by clicking [here](https://meritumnews.com/download).

## Known Bugs

All bugs, comments, and feedback can be reported at [feedback@meritumnews.com](mailto:feedback@meritumnews.com).

Bugs I'm aware of and will be fixed in the future:

- Incorrectly displayed notification icon (Android only, mainly on Samsung devices)
