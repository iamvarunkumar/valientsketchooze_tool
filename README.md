# Valientsketchooze Personal AI Generator Tool

## Description

This is a personal web-based utility built with Django and powered by the Google Gemini API. Its purpose is to assist with content creation for the Valientsketchooze digital artwork page by generating relevant text based on user input.

Currently, the tool can generate product descriptions for artwork. It's designed for personal use with plans for future integration into a larger website's admin dashboard.

**Current Status:** (End of Sprint 1) - Basic product description generation is functional.

## Features (Implemented)

* Generate a product description for digital artwork based on provided text context using the Google Gemini API (`gemini-1.5-flash` model).
* Basic web interface for submitting context and viewing the generated description.
* Asynchronous backend view using Django and Uvicorn.
* Secure handling of the Google API key via environment variables.

## Technology Stack

* **Backend:** Python, Django
* **AI Model:** Google Gemini API (`google-generativeai` SDK)
* **Server:** Uvicorn (for ASGI)
* **Frontend:** HTML, CSS, JavaScript (basic)
* **Environment Management:** python-dotenv

## Setup Instructions

1.  **Prerequisites:**
    * Python 3.9+
    * Git
2.  **Clone the Repository:**
    ```bash
    # Replace with your actual repository URL when you host it
    git clone <your-repository-url>
    cd valientsketchooze-tool
    ```
3.  **Create & Activate Virtual Environment:**
    ```bash
    python -m venv env
    # On macOS/Linux:
    source env/bin/activate
    # On Windows:
    .\env\Scripts\activate
    ```
4.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
5.  **Configure API Key:**
    * Obtain your API key from [Google AI Studio](https://aistudio.google.com/app/apikey).
    * Create a file named `.env` in the project root directory.
    * Add the following line to `.env`, replacing the placeholder with your key:
        ```dotenv
        GOOGLE_API_KEY='YOUR_ACTUAL_API_KEY'
        ```
    * Ensure `.env` is listed in your `.gitignore` file (it should be if you followed Sprint 0).
6.  **Database Migrations:**
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```
    *(This sets up the initial database, likely SQLite by default)*
7.  **Run Development Server:**
    ```bash
    uvicorn valientsketchooze_tool.asgi:application --reload
    ```
8.  **Access the Tool:** Open your browser and navigate to `http://127.0.0.1:8000` (or the address provided by Uvicorn).

## Usage (Current)

1.  Navigate to the main page (`/`).
2.  Enter context or details about the artwork in the text area provided.
3.  Click the "Generate Description" button.
4.  Wait a few moments for the AI to generate the text.
5.  The generated product description will appear below the form.

## Future Plans (Upcoming Sprints)

* Implement generation for Instagram Captions, Hashtags, and Product Tags.
* Provide 3 distinct options for each generation type.
* Enhance the UI for selecting generation type and displaying options.
* Add "Copy to Clipboard" functionality.
* (Optional) Implement history tracking for generated content.
* Refactor code for better maintainability and prepare for integration.
