# Flask Todo List Application

A simple and elegant todo list web application built with Flask and SQLAlchemy. This app allows users to create, read, update, and delete tasks with timestamps.

## Features

- ✅ Add new tasks
- ✏️ Update existing tasks
- 🗑️ Delete tasks
- 📅 Automatic timestamp tracking
- 💾 SQLite database for persistent storage

## Prerequisites

Before running this application, make sure you have Python installed on your system (Python 3.7 or higher recommended).

## Installation

1. Clone or download this repository to your local machine.

2. Install the required dependencies:

```bash
pip install flask flask-sqlalchemy
```

## Database Setup

Before running the app for the first time, you need to create the database:

1. Open a Python shell in the project directory:

```bash
python
```

2. Run the following commands:

```python
from app import app, db
with app.app_context():
    db.create_all()
exit()
```

This creates a `test.db` file in your project directory with the necessary table structure.

## Running the Application

Start the Flask development server:

```bash
python app.py
```

The application will be available at `http://127.0.0.1:5000/` in your web browser.

## Project Structure

```
.
├── app.py                 # Main application file
├── test.db               # SQLite database (created after setup)
└── templates/            # HTML templates directory
    ├── index.html        # Main page template
    └── update.html       # Update task template
```

## Application Routes

- `GET /` - Display all tasks
- `POST /` - Create a new task
- `GET /update/<id>` - Display update form for a specific task
- `POST /update/<id>` - Update a specific task
- `GET /delete/<id>` - Delete a specific task

## Database Model

The application uses a simple `Todo` model with the following fields:

- `id` - Primary key (auto-generated)
- `content` - Task description (max 200 characters)
- `date_created` - Timestamp of task creation (auto-generated)

## Configuration

The app uses SQLite as the database with the URI configured in `app.py`:

```python
app.config['SQLALCHEMY_DATABASE_URI'] = 'sqlite:///test.db'
```

You can modify this to use a different database location if needed.

## Development Mode

The application runs in debug mode by default, which provides:

- Auto-reload on code changes
- Detailed error messages
- Interactive debugger

**Note:** Debug mode should be disabled in production environments.

## Templates Required

This application requires two HTML templates in the `templates/` directory:

1. **index.html** - Should display all tasks and include a form to add new tasks
2. **update.html** - Should display a form to update an existing task

Make sure these templates are created and properly reference the task data passed from the Flask routes.

## Contributing

Feel free to fork this project and submit pull requests with improvements or bug fixes.

## License

This project is open source and available for educational purposes.