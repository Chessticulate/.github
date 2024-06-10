## Welcome to Chessticulate! This organization hosts several components related to our chess website, including a chess engine called Shallowpink, a chessticulate api built with FastAPI, and a worker pool service to validate moves using Shallowpink.

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
