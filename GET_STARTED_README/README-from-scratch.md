# Setting Up Flask + Electron from Scratch

Follow these steps to create a Flask + Electron project from scratch:

## Prerequisites
- Python installed on your system.
- Node.js and npm installed.

## Steps

### 1. Set Up Flask
1. Create a Python virtual environment:
   ```powershell
   python -m venv venv
   ```
2. Activate the virtual environment:
   ```powershell
   .\venv\Scripts\Activate
   ```
3. Install Flask:
   ```powershell
   pip install flask
   ```
4. Create a `app.py` file with the following content:
   ```python
   from flask import Flask

   app = Flask(__name__)

   @app.route('/')
   def home():
       return "Hello, Flask!"

   if __name__ == '__main__':
       app.run(debug=True)
   ```

### 2. Set Up Electron
1. Initialize a Node.js project:
   ```powershell
   npm init -y
   ```
2. Install Electron:
   ```powershell
   npm install electron --save-dev
   ```
3. Create a `main.js` file with the following content:
   ```javascript
   const { app, BrowserWindow } = require('electron');

   let mainWindow;

   app.on('ready', () => {
       mainWindow = new BrowserWindow({
           width: 800,
           height: 600,
           webPreferences: {
               nodeIntegration: true,
           },
       });

       mainWindow.loadURL('http://127.0.0.1:5000');
   });
   ```
4. Add a `start` script to `package.json`:
   ```json
   "scripts": {
       "start": "concurrently \"python app.py\" \"electron .\""
   }
   ```
5. Install `concurrently` for running Flask and Electron together:
   ```powershell
   npm install concurrently --save-dev
   ```
6. Install `electron-reload` for live updates:
   ```powershell
   npm install electron-reload --save-dev
   ```
7. Update `main.js` to include live reload:
   ```javascript
   require('electron-reload')(__dirname, {
       electron: require(`${__dirname}/node_modules/electron`)
   });
   ```

### 3. Run the Application
1. Start the Flask server and Electron app:
   ```powershell
   npm start
   ```
2. Your app will open in an Electron window, displaying the Flask backend.
