
# Postgres Q&A

Postgres Q&A is a project that demonstrates how to use word embeddings and Postgres to build a chatbot. The chatbot is implemented using Vercel Edge Functions and the @neondatabase/serverless driver, and relies on OpenAI's GPT-3 API to generate responses.

## Getting started
To get started with this project, you'll need to have:
- A Neon account, and project.
- an API key for the OpenAI GPT-3 API, which you can obtain from https://openai.com/.

Once you have the prerequisites installed, follow these steps to get the project up and running:

Clone the repository:

```bash
git clone https://github.com/neondatabase/postgres-qa.git
```
Install the project dependencies:

```bash
cd postgres-qa
npm install
```
Set the following environment variables:

OPENAI_API_KEY: Your OpenAI API key.
DATABASE_URL: The connection URL for your Neon database.

Create the `documents` and `openai_ft_data` tables in your Neon database by running the following command:

bash```
psql <database-url> -f database.sql
```
Start the server:

bash```
npm run dev
```
Use the chatbot by sending a POST request to the /api/askme endpoint with a JSON payload containing the query parameter:

json```
curl -X POST -H "Content-Type: application/json" \
  -d '{"query": "What is the meaning of life?"}' \
  http://localhost:3000/api/askme
```
The response will be a JSON object containing the answer parameter, which will be generated by the OpenAI GPT-3 API.

## Contributing
We welcome contributions to this project! If you find a bug, have a suggestion, or want to contribute code, please open an issue or pull request on the GitHub repository.

## License
This project is licensed under the MIT License. See the LICENSE file for more information.
