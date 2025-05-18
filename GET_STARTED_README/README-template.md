# Using the Flask + Electron Template

This template provides a pre-configured setup for integrating Flask and Electron. Follow these steps to get started:

## Prerequisites
- Python installed on your system.
- Node.js and npm installed.

## Steps to Use the Template

### 1. Install Dependencies
1. Activate the Python virtual environment:
   ```powershell
   .\venv\Scripts\Activate
   ```
2. Install Flask:
   ```powershell
   pip install flask
   ```
3. Install Node.js dependencies:
   ```powershell
   npm install
   ```

### 2. Run the Application
1. Start the Flask server and Electron app:
   ```powershell
   npm start
   ```
2. Your app will open in an Electron window, displaying the Flask backend.

## Features
- Flask backend for handling API requests.
- Electron frontend for a desktop application interface.
- Live reload for Electron using `electron-reload`.
- Concurrently running Flask and Electron for seamless development.

## File Structure
- `app.py`: Flask backend.
- `main.js`: Electron main process.
- `index.html`: Frontend HTML file.
- `styles.css`: Styling for the frontend.
- `package.json`: Node.js configuration file.

Enjoy building with Flask and Electron!
