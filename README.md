
# Full-Stack FastAPI and React Template
This is a template repository, featuring a full-stack application with FastAPI as the backend and ReactJS as the frontend, utilizing ChakraUI. This demo provides a hands-on example of how to set up and run a complete web application.

# Project Structure
The repository is organized into two main directories:

- **frontend**: Contains the ReactJS application.
- **backend**: Contains the FastAPI application and PostgreSQL database integration.

Each directory has its own README file with detailed instructions specific to that part of the application.

## Prerequisites
**General Prerequisites**
- Docker: Ensure Docker is installed and running on your machine.
- Docker Compose: Ensure Docker Compose is installed.

- **Frontend Prerequisites**
- Node.js: Version 14.x or higher
- npm: Version 6.x or higher

**Backend Prerequisites**
- Python: Version 3.10 or higher
- Poetry: For dependency management
- PostgreSQL: Ensure the database server is running


**Installing Poetry**
To install Poetry, follow these steps:

```sh

curl -sSL https://install.python-poetry.org | python3 -
```
Add Poetry to your PATH (if not automatically added).


### Running the App Locally
- **Frontend**
1. Navigate to the frontend directory:

```sh
cd frontend
```

2. Install dependencies:

```sh
npm install

```
3. Run the development server:

```sh
npm run dev
```
Configure API URL: Ensure the API URL is correctly set in the .env file.

- **Backend**
1. Navigate to the backend directory:

```sh

cd backend
```
2. Install dependencies using Poetry:

```sh
poetry install
```

3. Set up the database with the necessary tables:

```sh
poetry run bash ./prestart.sh
```
4. Run the backend server:

```sh
poetry run uvicorn app.main:app --reload
```
5. Update configuration: Ensure you update the necessary configurations in the .env file, particularly the database configuration.

### Using Docker Containers Locally
-**Frontend**
1. Navigate to the frontend directory:

```sh
cd frontend
```
2. Build the Docker image:

```sh

docker build -t frontend:latest .
```
3.Run the Docker container:

```sh

docker run -p 5173:5173 frontend:latest
```

-**Backend**
1. Navigate to the backend directory:

```sh
cd backend
```
2. Build the Docker image:

```sh
docker build -t backend:latest .
```
3. Run the Docker container:

```sh

docker run -p 8000:8000 backend:latest
```
### Using Docker Compose on an EC2 Instance
Ensure Docker, Docker Compose and git  are installed on your EC2 instance.

1. Clone the repository:
```sh
git clone https://github.com/laraadeboye/devops-stage-2.git
```
2. Navigate to the project directory:

```sh

cd /path/to/project
```
3. Build and run Docker Compose:

```sh
docker-compose up --build
```
This will build and start all the services defined in the docker-compose.yml file, including the frontend, backend, PostgreSQL database adminer and the proxy manager.

#### Additional Information
For more instructions, please refer to the respective README files in the frontend and backend directories.