![BeamMP Server Control](https://virtualtmp.com/yVxUKHlpy6nv.png)

This project provides a web-based GUI for controlling a BeamMP server, implemented using Flask. It allows you to manage active and inactive mods, configure server settings, and monitor connected users, all from a user-friendly interface hosted locally. The Web UI interacts directly with the BeamMP server files, moving mods between active and inactive states and editing the server configuration. It also includes a login system for secure access and real-time monitoring of server status and connected users. This setup is designed to be run on Windows machines.

## Preview

![Preview 1](https://virtualtmp.com/JCcYjOFMYwoz.png)
![Preview 2](https://virtualtmp.com/xVMR9pgVGgUx.png)
![Preview 3](https://virtualtmp.com/utHo3D6nV2XW.png)

## Features

- **Mod Management:** Easily activate and deactivate car and track mods.
- **Server Configuration:** Update server settings directly from the web interface.
- **User Monitoring:** View connected users and their details in real-time.
- **Server Control:** Start and stop the server with a toggle switch.

## Installation

### Prerequisites

- [Python 3.x](https://www.python.org/)
- [Flask](https://flask.palletsprojects.com/)
- [Flask-Login](https://flask-login.readthedocs.io/)
- [WTForms](https://wtforms.readthedocs.io/)
- [psutil](https://pypi.org/project/psutil/)
- [TOML](https://pypi.org/project/toml/)

**Don't be intimidated by all the prerequisites**, it's very easy to install once you have the latest version of Python installed.

### Steps

1. **Install Python**

   Download and install the latest version of Python from the [official Python website](https://www.python.org/).

2. **Download the Project Files**

   Download the project files from the provided .zip file and extract them to your desired location. The folder structure should look like this:

   ![Folder Structure Part 1](https://virtualtmp.com/Ag5CH0oiP28v.png)
   
   This is the default BeamMP server folder where we paste the "WebGUI" folder after it's extracted.

   ![Folder Structure Part 2](https://virtualtmp.com/cb7d22U8sddB.png)
   
   WebGUI folder structure

3. **Install Dependencies**

   Open a terminal or command prompt and navigate to the project directory. Then run:

   ```sh
   pip install flask flask-login wtforms psutil toml

4. **Note: Setup BeamMP Server**

   - The `Resources` folder in this package replaces the original `Resources` folder that comes with the downloaded BeamNG server package.
   - Ensure that the default `ServerConfig.toml` file remains in the main BeamMP Server directory.

5. **Configure Web GUI**

   - Update the `ServerConfig.toml` file inside the `WebGUI` folder to match your desired server settings.
   - The Web GUI will use this configuration file to control the server.
   - This `ServerConfig.toml` file can later be edited inside the GUI itself for ease of access.

6. **Generate and Set Secret Key**

   For the login page and authentication process, you need to generate a secret key and input it in the `app.py` file.

   - Create a new Python file named `generate_secret_key.py` with the following content:

     ```python
     import os
     print(os.urandom(24))
     ```

   - Open a terminal or command prompt, navigate to the directory where `generate_secret_key.py` is located, and run:

     ```sh
     python generate_secret_key.py
     ```

   - This will generate a secret key. Copy the generated key and set it in the `app.py` file:

     ```python
     app.config['SECRET_KEY'] = b'your_generated_secret_key'
     ```

   - Once the secret key is generated and saved in the `app.py` file, you can delete the `generate_secret_key.py` file.

7. **Update BEAMMP_DIR Path**

   Open the `app.py` file and update the `BEAMMP_DIR` variable on line 63 to reflect the directory where your BeamMP Server is extracted:

   ```python
   BEAMMP_DIR = r'C:/Users/Administrator/Desktop/BeamMP Server'  # Update this path

8. **Run the Web GUI**

   Run the Web GUI by executing the `StartWebUI.bat` file.

9. **Access the Web GUI**

   Open your web browser and navigate to `http://localhost:5000`. Use the following credentials to log in:

   - **Username:** admin
   - **Password:** admin

## Important Note

Initially, put all of your mods in the `/Resources/` folder and organize the mods into their respective `/Cars/` or `/Tracks/` folder. Then, through the Web GUI, activate whichever mods you require for your server. If you have mods that don't perfectly fit into either 'Cars' or 'Tracks', just put them in the `/Cars/` folder because you are able to select multiple mods in that section.

## Configuration

The `ServerConfig.toml` file inside the `WebGUI` folder is used to configure your server settings. You can update the following parameters through the web interface:

- `Name`
- `Port`
- `LogChat`
- `Tags`
- `Debug`
- `Private`
- `Max Cars`
- `Max Players`
- `Description`

## Usage

- **Activate/Deactivate Mods:** Use the interface to move mods between active and inactive states.
- **Start/Stop Server:** Use the toggle switch to start or stop the server.
- **Edit Configuration:** Update server settings through the configuration form.
- **Monitor Users:** View the list of currently connected users and their details.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to discuss any changes.

## Contact

For any questions or feedback, please reach out to me on here or message me "pclipse" on the BeamMP discord.
