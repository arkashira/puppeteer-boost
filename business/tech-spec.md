# tech-spec.md
## v1 Technical Specification

### Stack

* Language: Node.js (14.x)
* Framework: Express.js (4.x)
* Runtime: Docker (20.x)
* Database: MongoDB (4.x) with Mongoose (6.x) ORM
* Storage: AWS S3 (for storing and serving assets)

### Hosting

* Free-tier-first: Yes
* Platforms:
	+ AWS: EC2 (t2.micro), RDS (db.t2.micro), S3
	+ DigitalOcean: Droplet (512MB), Database (20GB), Spaces
	+ Heroku: Hobby dyno, PostgreSQL (Hobby), Add-on storage

### Data Model

* Tables/Collections:
	+ `users`: stores user information (username, email, password)
	+ `bots`: stores bot information (name, description, Puppeteer settings)
	+ `logs`: stores logs for bot runs (timestamp, bot name, log message)
	+ `metrics`: stores metrics for bot runs (timestamp, bot name, metric value)
* Key Fields:
	+ `users`: `id` (primary key), `username`, `email`, `password`
	+ `bots`: `id` (primary key), `name`, `description`, `puppeteer_settings`
	+ `logs`: `id` (primary key), `timestamp`, `bot_name`, `log_message`
	+ `metrics`: `id` (primary key), `timestamp`, `bot_name`, `metric_value`

### API Surface

* Endpoints:
	1. **GET /bots**: retrieve a list of all bots
		- Method: GET
		- Path: `/bots`
		- Purpose: retrieve a list of all bots
	2. **POST /bots**: create a new bot
		- Method: POST
		- Path: `/bots`
		- Purpose: create a new bot
	3. **GET /bots/{id}**: retrieve a bot by ID
		- Method: GET
		- Path: `/bots/{id}`
		- Purpose: retrieve a bot by ID
	4. **PUT /bots/{id}**: update a bot by ID
		- Method: PUT
		- Path: `/bots/{id}`
		- Purpose: update a bot by ID
	5. **DELETE /bots/{id}**: delete a bot by ID
		- Method: DELETE
		- Path: `/bots/{id}`
		- Purpose: delete a bot by ID
	6. **GET /logs**: retrieve a list of all logs
		- Method: GET
		- Path: `/logs`
		- Purpose: retrieve a list of all logs
	7. **GET /logs/{id}**: retrieve a log by ID
		- Method: GET
		- Path: `/logs/{id}`
		- Purpose: retrieve a log by ID
	8. **GET /metrics**: retrieve a list of all metrics
		- Method: GET
		- Path: `/metrics`
		- Purpose: retrieve a list of all metrics
	9. **GET /metrics/{id}**: retrieve a metric by ID
		- Method: GET
		- Path: `/metrics/{id}`
		- Purpose: retrieve a metric by ID
	10. **POST /login**: authenticate a user
		- Method: POST
		- Path: `/login`
		- Purpose: authenticate a user

### Security Model

* Authentication: JSON Web Tokens (JWT) with refresh tokens
* Authorization: Role-based access control (RBAC) with three roles: admin, user, guest
* Secrets: store sensitive data (e.g. API keys, database credentials) using environment variables
* IAM: use AWS IAM or DigitalOcean IAM to manage access to resources

### Observability

* Logs: use Winston (3.x) logging library with MongoDB as the log store
* Metrics: use Prometheus (2.x) with Grafana (7.x) for visualization
* Traces: use OpenTelemetry (0.x) with Jaeger (2.x) for distributed tracing

### Build/CI

* Build tool: npm (6.x) with yarn (1.x) as the package manager
* CI tool: GitHub Actions (2.x) with Node.js (14.x) as the runtime
* Testing framework: Jest (26.x) with Enzyme (3.x) for unit testing and integration testing
* Code coverage: use Istanbul (5.x) with Jest (26.x) for code coverage reporting