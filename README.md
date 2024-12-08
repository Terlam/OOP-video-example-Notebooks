# README

## Overview

This Jupyter Notebook provides a hands-on lesson in the fundamental principles of Object-Oriented Programming (OOP) using a practical scenario: creating a mock streaming service that fetches and plays TV show episodes via the [TVmaze API](https://www.tvmaze.com/api). The notebook introduces the four core OOP principles—**Encapsulation**, **Abstraction**, **Inheritance**, and **Polymorphism**—and demonstrates how these concepts can be applied to real-world code.

By the end of this lesson, you will understand how to structure your code using OOP concepts and interact with an external API to create a simulated streaming experience. This experience involves searching for TV shows, retrieving their episodes, and playing them within a Python environment, all while maintaining clean and modular code design.

## Learning Objectives

1. **Understand OOP Fundamentals**  
   You’ll learn about classes, objects, methods, attributes, and how to apply OOP’s four main principles (Encapsulation, Abstraction, Inheritance, Polymorphism).

2. **Working with the TVmaze API**  
   Learn how to send HTTP requests to fetch data about TV shows and episodes, then integrate this data into classes that model a streaming service’s functionality.

3. **Designing Classes for a Streaming Service**  
   You’ll see how to represent shows and episodes as classes, encapsulating data and behavior in objects. For instance, the `Video` class sets a foundational structure, while the `Episode` class builds upon it to represent episodes with details like name, runtime, and images.

4. **Refactoring and Extensibility**  
   As you learn OOP principles, you’ll notice how the code can be easily extended. For example, adding new features (like watchlists or user profiles) can be done without rewriting large parts of the code, thanks to good OOP design.

## Prerequisites

- **Python 3.7 or higher**  
- **Jupyter Notebook** (installable via `pip install notebook` or through Anaconda)
- **Basic Python Knowledge**: Familiarity with Python syntax, data structures (lists, dicts), and function definitions.
- **Internet Connection**: Required for making calls to the TVmaze API.

No authentication keys are needed since the TVmaze API is publicly accessible.

## File Contents

- **`<this_notebook>.ipynb`**: The main Jupyter Notebook containing:
  - **Markdown cells**: Explaining OOP principles and how they apply to the code.
  - **Code cells**: Defining classes (`Video`, `Episode`, `Series`, `Theater`) and demonstrating OOP concepts.
  - **Interactive prompts**: Input prompts that let you search for a TV show and play its episodes.

## Running the Notebook

1. **Clone or Download**: Obtain the `.ipynb` file and the associated Python environment.
   
2. **Install Dependencies**:  
   ```bash
   pip install requests
   ```
   
   This ensures you have the `requests` library for making HTTP calls to the TVmaze API.

3. **Start Jupyter Notebook**:  
   ```bash
   jupyter notebook
   ```
   
   Open the notebook in your browser and run the cells sequentially.

## Step-by-Step Guide

1. **Introduction to OOP Principles**  
   The notebook starts by explaining the four principles of OOP:
   - **Encapsulation**: Restricting access to internal states and requiring all interaction to occur through defined methods.
   - **Abstraction**: Hiding implementation details and showing only the necessary interface.
   - **Inheritance**: Creating new classes that reuse, extend, and modify behaviors of existing classes.
   - **Polymorphism**: Allowing objects of different classes to be treated as objects of a common superclass, making code more flexible.

2. **Encapsulation**  
   The `Video` class demonstrates encapsulation by defining attributes (like `name`, `length`, `link`) and methods (`play`, `pause`) that manage internal state while preventing arbitrary modification from outside code.

3. **Abstraction**  
   The `Episode` class extends `Video` but introduces more complexity (e.g., retrieving data from the API, parsing JSON details) in a way that’s hidden from the user of the class. The details of how an episode’s information is fetched and stored are encapsulated, while the user just sees methods and attributes that provide the data they need.

4. **Inheritance**  
   `Episode` inherits from `Video`. This means `Episode` objects can do everything a `Video` can, plus more. Similarly, `Series` uses `Episode` objects internally. The `Series` class manages a collection of `Episode` objects, demonstrating how multiple classes work together.

5. **Polymorphism**  
   By treating different objects similarly—`Episode` instances are handled through methods that could also apply to `Video`—the code shows how polymorphism can simplify and generalize actions like “play” for different types of video-like objects.

6. **Interacting with the API**  
   The `Series` class fetches shows from the TVmaze API using user input. Once a show is found, it retrieves episodes and instantiates `Episode` objects. This step demonstrates how OOP can structure and manage external data sources.

7. **The Theater Class and User Interaction**  
   The `Theater` class simulates a user environment:
   - Manage multiple users and their watchlists.
   - Add new shows by searching through the API.
   - Play episodes from the watchlist.
   
   This provides a more realistic context: multiple layers of abstraction and classes working together seamlessly.

8. **Running the Simulation**  
   By running the `Theater` object’s `run()` method, you enter an interactive loop where you:
   - Create a user profile.
   - Search for shows.
   - Add them to your watchlist.
   - Play episodes from selected shows.
   
   All this interaction is guided by the underlying OOP structure.

## Exercises

- **Exercise 1:**  
  Consider what other classes might improve this streaming service. For example:
  - A `User` class that holds preferences and a watchlist.
  - A `Watchlist` class to handle adding, removing, and listing shows separately.
  - A `PremiumSeries` subclass that might offer additional features (e.g., bonus content).
  
  Try creating these classes and integrating them into the existing structure. Experiment with different OOP patterns to see how easily the system can be extended.

## Additional Resources

- [TVmaze API Documentation](https://www.tvmaze.com/api)
- [Python Classes and Objects (W3Schools)](https://www.w3schools.com/python/python_classes.asp)
- [Real Python’s OOP Tutorials](https://realpython.com/python3-object-oriented-programming/)

---

By working through this notebook, you’ll gain an intuitive grasp of OOP principles and how they can be used to organize complex, data-driven applications. Enjoy exploring and extending your pretend streaming service!
