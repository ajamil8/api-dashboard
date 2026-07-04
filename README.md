**API Dashboard Project**

This project is designed to simulate a dashboard that loads in data from a public weather API, as well as a PostgreSQL database. 

**Backend**

The backend is engineered using Spring Boot/JPA, which allows handling HTTP routing, creating a database, and outlining the program efficiently. Specifically JPA is used to create Item, which is a JPA entity that is mapped to a database table. It has attributes such as id (primary key), name, description, and status. Spring Boot helps create the REST API Controller and Service layer, ensuring that the server is able to communicate properly. 

ItemRepository is an interface the extends the JpaRepository interface, which has built-in CRUD methods, such as save(), findAll(), delete(), etc. Additionally, Spring Data JPA generates SQL queries automatically, eliminating the need to write any queries for this project.

ItemService is a class that handles the main business logic. It calls upon ItemRepository to use the methods mentioned before. This way, we're able to modify the the Item table as needed.

ItemController handles the HTTP functions. Specifically, GET, POST, and DELETE. ItemController associates the methods above with the HTTP functions. For example, GetMapping will call getAll() and return all of the entries in the Item table. 

**Frontend**

The frontend was created using React. I used Vite to structure the React project. From there, I created an App function that served as the main dashboard and loaded in two resuable components, WeatherWidget and ItemTable.

WeatherWidget displays New York's current weather using a Weather API. ItemTable displays the Item table by fetching data from the localhost set up for the API created for it. I created a few functions, such as handleAdd and handleDelete, which were implemented into buttons that could add/remove entries from the item table. I used axios to fetch data from the respective APIs, which is returned as JSON. I incorporated state management by using useEffect to fetch data from the APIs and useState to store the response so React can display and update it automatically. 
