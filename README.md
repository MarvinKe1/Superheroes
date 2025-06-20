## Superheroes
## Hero Powers API (Flask Backend)
This is a simple Flask-based backend API for managing fictional superheroes and their powers. The project includes basic endpoints for retrieving, updating, and assigning powers to heroes using a join model.

## Project Structure
Heroes_Postman
├── app.py          # Main Flask app and routes
├── models.py       # SQLAlchemy models
├── seed.py         # Populates database with sample data
├── migrations/     # Flask-Migrate files
└── app.db          # SQLite database file

## Technologies Used
Python 3
Flask
Flask-SQLAlchemy
Flask-Migrate
SQLite

Features
View a list of all heroes

View a single hero and their powers

View all available powers

Edit a power's description

Assign a power to a hero with a specific strength (via a join table)

## Setup Instructions
Clone the repo
git clone 
cd hero-powers-api/server
## Set up and activate a virtual environment
python3 -m venv venv
source venv/bin/activate
## Install required packages
pip install -r requirements.txt
## Initialize the database
flask db init
flask db migrate -m "Initial migration"
flask db upgrade
## Seed the database
python seed.py
## Run the application
flask run
Available Routes
 Heroes
GET /heroes
Returns a list of all heroes.

GET /heroes/<int:id>
Returns details for a single hero and their powers.

 Powers
GET /powers
Lists all powers.

GET /powers/<int:id>
Returns details for a single power.

PATCH /powers/<int:id>
Updates the description of a specific power.

Hero Powers (Join Table)
POST /hero_powers
Assigns a power to a hero with a strength.

Request Body:
{
  "strength": "Strong",
  "power_id": 1,
  "hero_id": 3
}
Valid Strength Values: "Strong", "Weak", "Average"

## Data Validation
Powers must have a non-empty description.

strength must be one of "Strong", "Weak", or "Average".

On invalid input, the API returns a 400 status with an error message.

## Notes
The app uses SQLite for development. You can switch to PostgreSQL by updating the database URI.

Code is designed for educational/demo use, not production.

No authentication/authorization is implemented.

## Contribution
Contributions are welcome!
To contribute:
Fork the repository
Create a new branch (git checkout -b feature/your-feature)
Commit your changes
Push to your branch and open a Pull Request
 ## Security Note
Passwords are stored as plain text in this demo project. In real applications, always hash passwords using libraries like bcrypt.

## Author
Marvin Mango 

## License
This project is licensed under the Moringa School License.
