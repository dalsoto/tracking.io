# tracking.io
tracking app


1. **Setting Up the Project:**
   - Started a new Flask project to create a web application.
   - Used the Flask framework because it's lightweight, easy to use, and well-suited for small to medium-sized web applications.

2. **Environment Variables and `.env` File:**
   - Used the `python-dotenv` library to load environment variables from a `.env` file.
   - This is a good practice to keep sensitive information, such as API keys and secrets, out of your code and in a separate, secure file.

3. **Flask App Initialization:**
   - Initialized a Flask web application using `Flask(__name__)`.
   - The `__name__` argument is a Python predefined variable that represents the name of the current module. Flask uses this to determine the root path of the application.

4. **Spotify OAuth Configuration:**
   - Configured Spotify OAuth using the `spotipy` library.
   - Created a `SpotifyOAuth` object with your Spotify app's client ID, client secret, redirect URI, and the desired scope (`'user-read-recently-played'`).
   - This allows your application to authenticate users with Spotify and access their recently played tracks.

5. **Defining Routes and Functions:**
   - Defined three routes in your Flask application:
      - `/`: Displays a welcome message with a link to log in with Spotify.
      - `/login`: Redirects the user to the Spotify authorization page.
      - `/callback`: Handles the Spotify callback after the user logs in.

6. **Handling the Callback:**
   - In the `/callback` route, you obtain the access token from Spotify using the `sp_oauth.get_access_token` method.
   - You use the access token to make requests to the Spotify API, specifically fetching the user's recently played tracks.

7. **Processing Tracks:**
   - For each track in the recently played tracks, you extract relevant information such as the track name, artist name, and album name.
   - You store this information in a list (`tracks`).

8. **Rendering HTML Template:**
   - You pass the list of tracks to an HTML template (`recent_tracks.html`) for rendering.
   - This template uses Jinja2 templating syntax to display the track information.

9. **Running the Application:**
   - If the script is executed directly (not imported as a module), the Flask application is run with the `app.run(debug=True)` line.

10. **HTML Template (`recent_tracks.html`):**
   - The template receives the list of tracks and dynamically generates HTML to display the track information.
   - Made adjustments to the template to display the artist along with the song name and removed the timestamp.

11. **CSS Styling:**
   - Added a simple CSS file (`styles.css`) to style your HTML template.

12. **SQLite Database (Optional):**
   - Initially, you had code to store the tracks in an SQLite database (`listening_history.db`). However, due to issues, we temporarily removed that part.

13. **Debugging and Iteration:**
   - Throughout the process, I encountered errors and made iterative changes to address them.
   - Debugging involved checking the terminal output, understanding error messages, and refining the code.

14. **Current State:**
   - The application now allows users to log in with Spotify, view their recently played tracks (without timestamps), and see the artist along with the song name.

15. **Remaining Steps:**
   - Considering adding the functionality to store tracks in a database and checking whether SQL is installed.
