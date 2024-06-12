# Welcome to Chessticulate!

This organization encompasses all of the components comprising our chess website (as well as a few false-starts and experiments). The primary components of Chessticulate are:
- [shallow-pink](https://github.com/chessticulate/shallow-pink): A chess engine written in javascript 
- [chess-workers](https://github.com/chessticulate/chess-workers): A scalable REST API wrapper for shallowpink 
- [chessticulate-api](https://github.com/chessticulate/chessticulate-api): The api for the chessticulate website built with FastAPI

## The Story

I ([bglaws](https://github.com/bglaws)) became enamored with the game of Chess, [as many of us did](https://www.chess.com/blog/CHESScom/chess-is-booming-and-our-servers-are-struggling), during the peak of the COVID-19 pandemic. I was also still in college learning Java at the time, and these two interests of mine merged and blossomed into a [terminal chess program](https://github.com/bglaws/chess) I built. Later on I began learning JavaScript at an internship. That, combined with a dissatisfaction with the chess programming I had done previously, led me to make a second attempt at writing an improved chess engine, this time in JavaScript. Yes, JS is probably not the most efficient option in hindsight (especially if you want to add AI into the mix), but I really wanted to improve my JavaScript skills. Additionally, I had some vague ideas of building my own simple chess website (for fun of course), and so building the engine in JS would allow it to be used on the frontend of such a site.

After some time developing that I decided to collaborate with my brother [krglaws](https://github.com/krglaws) on building the chess website I had been picturing. This project is the product of that collaboration.

## Where We're At

- shallow-pink [(it's a pun)](https://en.wikipedia.org/wiki/Deep_Blue_(chess_computer)) - Our JavaScript chess engine. It is more or less "done". The core functionality is there, and it is fully tested. It includes a rudimentary AI that has been implemented using a simple Minimax algorithm. We have tentative plans to:
  - reimplement the library in either C or C++.
  - improve upon the ai using a Monte Carlo Tree Search or Neural Network, or both.

- chessticulate-api - The REST API for our website. We decided to write our API in Python using the FastAPI web framework since it comes with excellent data validation and auto-generated swagger pages. The database we are using for now is sqlite, although we have plans to migrate to postgres at some point. This part of the project is mostly done, barring whatever additions or enhancements we decide to add later on.

- chess-workers - A small expressjs REST API wrapper around shallow-pink.

Our reasoning for separating shallow-pink from the python API via chess-workers (aside from the fact that they are written in different languages) is as follows:
  1. by having shallow-pink, which requires significant CPU resources, execute in a separate process from the python API and moving shallow-pink to an IO-bound process instead of a CPU-bound process (at least from python's perspective), we avoid holding up FastAPI's eventloop.
  2. it is easier to scale a project when it has been broken up into simpler components.

## TODO

We are currently working on deploying the components we have with Docker onto a raspberry pi. After that, our next step is to build the frontend, probably with React.

<!--

**Here are some ideas to get you started:**

🙋‍♀️ A short introduction - what is your organization all about?
🌈 Contribution guidelines - how can the community get involved?
👩‍💻 Useful resources - where can the community find your docs? Is there anything else the community should know?
🍿 Fun facts - what does your team eat for breakfast?;
🧙 Remember, you can do mighty things with the power of [Markdown](https://docs.github.com/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)

Repositories
1. Shallowpink
Shallowpink is our custom chess engine designed to evaluate and generate chess moves. It serves as the core computational engine behind the Chessticulate project.

Features:
Implements standard chess rules
Provides move generation and evaluation
Lightweight and efficient
2. API
Our API, built with FastAPI, provides a web interface to interact with Shallowpink. This allows developers to integrate our chess engine into their applications seamlessly.

Features:
Endpoints for move validation, game state management, and more
High performance and scalability
Comprehensive documentation
3. Worker Pool
The Worker Pool service uses Shallowpink to validate chess moves requested through the API. This ensures that move validation is handled efficiently and can scale with demand.

Features:
Manages a pool of worker processes for concurrent move validation
Integrates seamlessly with the FastAPI service
Optimized for high throughput and low latency
Getting Started
Prerequisites
Python 3.8+
FastAPI
Docker (optional, for containerized deployment)
Installation
Clone the repositories:

bash
Copy code
git clone https://github.com/Chessticulate/Shallowpink.git
git clone https://github.com/Chessticulate/API.git
git clone https://github.com/Chessticulate/WorkerPool.git
Install dependencies for each project:

bash
Copy code
cd Shallowpink
pip install -r requirements.txt

cd ../API
pip install -r requirements.txt

cd ../WorkerPool
pip install -r requirements.txt
Running the Projects
Start the Shallowpink engine:

bash
Copy code
cd Shallowpink
python main.py
Run the FastAPI service:

bash
Copy code
cd ../API
uvicorn main:app --reload
Launch the Worker Pool:

bash
Copy code
cd ../WorkerPool
python worker_pool.py

-->
