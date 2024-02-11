# Polls API

## Description

During the Rocketseat's NLW event week, I developed a polls API. The event provided an immersion into the latest technologies, focusing especially on Node.js, Docker, Prisma, and Fastify. Additionally, I had the opportunity to explore WebSocket concepts and enhance my Node.js skills.

#

## Documentation

The poll application is an API designed to create, view, vote and manage polls. This documentation provides a step-by-step guide on how to use the API effectively.

## Environment Setting

#### Clone the application repository from GitHub:

```bash
git clone https://github.com/Gustavo-Leite/polls-node-api.git
```

#### Navigate to the application directory:

```bash
cd polls-node-api
```

#### Install project dependencies:

```bash
npm install
```

#### Rename the ".env.example" file in the root to ".env"

```bash
mv .env.example .env
```

#### Make sure you have Docker installed on your system. If not, follow the installation instructions on the [official Docker website](https://www.docker.com/get-started/). After installing Docker, start the Docker environment:

```bash
docker-compose up -d
```
#### This will start the containers needed for the database and other services used by the application. With these steps, you will have the application and its execution environment ready to use.

#### Run database migrations to create the required tables:

```bash
prisma migrate dev
```

## Running the app

#### After configuring the database, you can start the application server:

```bash
npm run dev
```

#### The server will be available at http://localhost:3333

## Using the API

#### Make sure you have some API testing software to easily interact with the provided endpoints. There are several options available, including [Postman](https://www.postman.com/downloads/), [Insomnia](https://insomnia.rest/download) and [Hoppscotch](https://hoppscotch.io/). These tools offer intuitive interfaces for sending HTTP requests, viewing responses, and testing different API endpoints. Choose the software that best suits your preferences and start exploring the API features without any hassle.
#### The API has the following endpoints available:

### Create a new poll

POST http://localhost:3333/polls

##### Put this json in the body of the request.
```JSON
{
  "title": "Poll title",
	"options": ["Option1", "Option2", "Option3", "Option4", "Option5"]
}
```

### Take all available polls.

GET http://localhost:3333/polls/(poll_id_from_previous_POST_request)

```JSON
{
	"poll": {
		"id": "xxxxxxxxxxxxxxxxxxxxxxxxx",
		"title": "Poll title",
		"options": [
			{
				"id": "yyyyyyyyyyyyyyyyyyyyyyy1",
				"title": "Option1",
				"score": 0
			},
			{
				"id": "yyyyyyyyyyyyyyyyyyyyyyy2",
				"title": "Option2",
				"score": 0
			},
			{
				"id": "yyyyyyyyyyyyyyyyyyyyyyy3",
				"title": "Option3",
				"score": 1
			},
			{
				"id": "yyyyyyyyyyyyyyyyyyyyyyy4",
				"title": "Option4",
				"score": 0
			},
			{
				"id": "yyyyyyyyyyyyyyyyyyyyyyy5",
				"title": "Option5",
				"score": 0
			}
		]
	}
}
```

### Register your vote in a poll

POST http://localhost:3333/polls/(pollId)/votes

Put this json in the body of the request.
```JSON
{
	"pollOptionId": "(option_id)"
}
```

</body>
</html>
