# MapsGatherer
Small App helping people find the most practical meetup point based of distances

💡 Project Overview
Build a web application that helps users find bars in Paris based on the geolocation of multiple people.
Users should be able to input multiple geolocation points (e.g., from different friends) on a map, and the application will calculate and display bar suggestions closest to all users.

🧭 Core Requirements
🗺️ Functionality
Allow users to:

Input multiple geolocation points via an interactive map.

Receive a list of suggested bars based on proximity to all provided locations.

Bars data may be mocked, but:

You must explain in detail how this data would be obtained and accessed in a real-world scenario (e.g., API like OpenStreetMap, Google Places, or data scraping).

📍 Geolocation Logic
Implement a core algorithm to calculate the optimal bar(s) for a group based on multiple coordinates.

Include unit tests for this logic.

🧑‍💻 Frontend (Client)
Must be built with React.

You are free to choose between:

CSR (e.g., Vite + React)

SSR or hybrid frameworks (e.g., Next.js, Remix). Justify your choice.

UI/UX can be minimal; focus is on functionality.

Users should:

Input geolocation points (e.g., via map + form)

See the resulting bar list

🛠️ Backend (API)
Implement a RESTful API in your preferred language (Go is preferred).

The API should:

Accept geolocation inputs

Process and return relevant bar suggestions

Expose authentication endpoints

Must include:

JWT-based authentication (Google OAuth is a bonus)

OpenAPI-style API documentation (preferably auto-generated, e.g., with Swagger)

🗃️ Data Management
Use a relational or document-oriented database of your choice to store bar information (even mocked). You will need to:

Justify your DB selection

Explain schema structure (if applicable)

Implement a key-value store (e.g., Redis) for caching geolocation computations or frequent queries.

🚢 Infrastructure & Deployment
The full stack must be:

Containerized using Docker

Easily runnable locally (e.g., with docker-compose)

Preferably:

Deploy the application to a remote environment (e.g., AWS, Render, Railway). If any deployment cost is involved, notify the team.

Include:

Setup instructions

Environment variables management strategy

🧪 Testing Expectations
Minimum:

Unit tests for core geolocation logic

Bonus:

Integration tests

Show reasoning on which layers deserve test coverage (e.g., DB access, API integration, caching)

📦 Deliverables
Source code (frontend + backend)

Docker setup for local dev

Deployment (optional but preferred)

README including:

Architecture diagram (optional)

Setup & usage instructions

Explanation of data sourcing, DB/cache choices, and key trade-offs

Notes:
Look into GORM for SQL lib https://gorm.io/docs/

API routes:
Can this lead to security issues?
Yes, if you don’t secure your API routes.
Anyone can send requests to your API endpoints unless you add authentication and authorization.
Sensitive logic, secrets, and database access should always be handled server-side (in the API route), never in the client code.
Always validate and sanitize input on the server.

ACID:
Atomicity: All parts of a transaction succeed or none do.
Consistency: The database remains in a valid state before and after the transaction.
Isolation: Transactions don’t interfere with each other; intermediate states are hidden.
Durability: Once a transaction is committed, it won’t be lost, even if there’s a crash.

Check what GRPC


// ROOM FOR IMPROVEMENTS
I'm looking a bit ahead but thinking of improvements for the app. Adding other meeting places than bars. Coffes, restaurants, parks, shopping mall, gym...
another feature would be to have a slide that allows the app to get bars less centered. Like you could say, it's ok if one person has to do 10% more travel than others and so on.
Right now the app would be simple and only handle bird eye view. I would love to handle actual travelling time, walking distance, using public transport etc...
Going even further we could find the most agreable bars on different paths not only the shortest if other meeting points are not much longer to reach
Lastly, I would love for users to be able to add favorites or tag some restaurants like "vegan" so that they can only see the places they have toggled filters for