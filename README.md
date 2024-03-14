This project retrieves and analyzes tweets about the Russo-Ukrainian War. It uses techniques like text processing, Exploratory Data Analysis, tf-idf indexing, and Word2Vec ranking to understand the content of the tweets. The project also includes a Search Engine WebApp with a built-in web analytics section for further data exploration. You can input queries and the system will rank the tweets based on their relevance. The Tweet2Vec ranking is not used in the final version of the search engine web, but it has been successfully used for local benchmarking.

## Starting the Web App

```bash
python -V
# Make sure we use Python 3

cd search-engine-web-app
python web_app.py
```
The above will start a web server with the application:
```
 * Serving Flask app 'web-app' (lazy loading)
 * Environment: production
   WARNING: This is a development server. Do not use it in a production deployment.
   Use a production WSGI server instead.
 * Debug mode: off
 * Running on http://127.0.0.1:8088/ (Press CTRL+C to quit)
```

Open Web app in your Browser:  
[http://127.0.0.1:8088/](http://127.0.0.1:8088/) or [http://localhost:8088/](http://localhost:8088/)

- The UI of the search engine was crafted to provide a simple and efficient user experience. The search interface was designed with clarity in mind, featuring a straightforward layout with a prominent search bar, enabling users to enter their queries with minimal distraction. This design choice was motivated by the need to create an environment where users could focus on their search tasks without unnecessary complexity or clutter.

- In displaying search results, attention was paid to both aesthetics and functionality. Each result was presented in a clean and organized manner, making it easy for users to scan through the information and identify relevant results. The use of well-defined sections, clear typography, and spacing contributed to the readability and overall user-friendliness of the results page. This approach not only enhanced the visual appeal of the application but also improved usability, a key factor in user satisfaction.

- Clickable elements in the search results were designed to be intuitive, encouraging user interaction while simultaneously facilitating the collection of valuable click data. This feature was subtly incorporated into the UI, ensuring that it did not disrupt the user experience or detract from the primary functionality of the search engine.

- For data collection and storage, an in-memory storage mechanism was chosen. This decision was made to simplify the replication process bypassing the complexities associated with setting up and managing a database. Custom data models for Sessions, Clicks, and Requests were developed within the Python and Flask framework, reflecting a preference for a straightforward and accessible development environment conducive to rapid prototyping. While this approach was ideal for demonstration and educational purposes, it was recognized that a persistent database solution would be more appropriate for real-world applications where data durability and scalability are crucial.

- Session management was enhanced to ensure accurate and reliable user tracking. This involved creating unique session IDs for each user visit and implementing logic to prevent the creation of duplicate session entries for the same user. The use of UUIDs guarantees the uniqueness of each session, which is critical for tracking user activities accurately. The rationale behind this was to avoid the inflation of user session counts and ensure that the web analytics data reflected genuine user interactions. In conclusion, the development choices made in the project were carefully considered to provide a balance between educational value, ease of implementation, and the potential for offering meaningful insights into user behavior and application performance. The result was a functional Flask web application prototype, equipped with fundamental web analytics capabilities, and serving as a solid foundation for more advanced developments.


  ### Importance of Chosen Metrics

The selection of metrics and the motivation behind data collection in the Flask web application were grounded in the objectives of enhancing user experience, improving search functionality, and providing meaningful insights into user behavior.


1. Session Data (User IP, Location, User Agent): Collecting session data is fundamental for understanding user demographics and behavior. Information like user IP, geographical location, and user agent provides insights into the diversity of the user base, their geographical distribution, and the devices or browsers used. This data is crucial for optimizing the application for different user segments and ensuring compatibility across various platforms.

2. Request Data (Queries, Timestamps): Tracking search queries and their timestamps enables the analysis of search trends, popular search terms, and user engagement over time. Understanding what users are searching for is vital for refining the search algorithm and ensuring that it aligns with user needs and expectations. Timestamp data helps in analyzing peak usage times, which can inform infrastructure scaling decisions and maintenance scheduling.

3. Click Data (Document Clicks, Related Queries, Ranking): Monitoring which documents are clicked, the associated queries, and their rankings in the search results yields valuable insights into the effectiveness of the search algorithm. It helps in assessing whether the most relevant and useful results are being presented to the users. This data is also instrumental in improving search result ranking algorithms.


 ### Bonus:

We implemented geolocalization based on the IP, but given that we are currently running the server locally it wasn't of much use.
