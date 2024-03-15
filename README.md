# Report on Using Restful-booker API with Postman

## Introduction:
Testing APIs is a critical practice to ensure their correct functioning and the integrity of the systems that use them. Postman is a widely used tool for testing APIs due to its ease of use and comprehensive features. In this report, we will explore the use of the Restful-booker API in conjunction with Postman to demonstrate how to create a collection of requests, export it, and share it through a case study.

## Methods:
1. **Creation of Collection in Postman:**
   - Initially, we created a new collection in Postman named "Restful-booker API Collection".
   - We added requests for the different operations available in the Restful-booker API, such as creating a booking, updating a booking, fetching bookings, among others.

2. **Testing of Requests:**
   - We used Postman to test each request individually, ensuring that the responses are as expected.
   - We made sure that the parameters and headers of the requests are correctly configured to avoid errors during testing.

3. **Exporting the Collection:**
   - We exported the collection created in Postman in JSON format, naming the file "restful_booker_collection.json".

4. **Creating the Repository and Uploading the Collection:**
   - We created a repository on GitHub to host the exported collection.
   - We uploaded the JSON file of the collection to the repository, making it available for sharing and collaboration.

## Results:
After following the methods described above, we obtained the following results:
- A collection in Postman containing requests to interact with the Restful-booker API.
- Each request was tested individually to ensure its correct functioning.
- The collection was exported to a JSON file and hosted in a repository on GitHub.

## Case Study:
Imagine a development team working on a hotel reservation application. They need to integrate the Restful-booker API to allow users to make reservations through the application. Using the Postman collection we created, the team can:
- Import the collection into their development environment in Postman.
- Test all functionalities of the Restful-booker API before integrating it into the application.
- Identify and fix any issues or bugs in the requests before the application's release.
- Share the collection among team members to facilitate collaboration and ensure consistency in testing.

## Conclusion:
In this report, we demonstrated how to use Postman to interact with the Restful-booker API, from creating the collection to exporting and sharing it via GitHub. Through a case study, we illustrated how this approach can be beneficial for development teams needing to integrate APIs into their projects, enabling efficient testing and ensuring the quality of the software delivered to users.


# Creation of the Test Suite with Postman:
Let's create a test suite in Postman that will cover all endpoints from the Restful-booker API documentation.

Endpoints to be covered:

Create Booking
Update Booking
Get Booking
Get All Bookings
Delete Booking

```
// Tests for the endpoint "Create Booking"
pm.test("Create Booking Test", function () {
    pm.response.to.have.status(200);
    pm.expect(pm.response.json().bookingid).to.be.a('number');
});

// Tests for the endpoint "Update Booking"
pm.test("Update Booking Test", function () {
    pm.response.to.have.status(200);
    pm.expect(pm.response.json().firstname).to.eql("John");
});

// Tests for the endpoint "Get Booking"
pm.test("Get Booking Test", function () {
    pm.response.to.have.status(200);
    pm.expect(pm.response.json().firstname).to.eql("John");
});

// Tests for the endpoint "Get All Bookings"
pm.test("Get All Bookings Test", function () {
    pm.response.to.have.status(200);
    pm.expect(pm.response.json().bookings.length).to.be.above(0);
});

// Tests for the endpoint "Delete Booking"
pm.test("Delete Booking Test", function () {
    pm.response.to.have.status(201);
});

```

# Report generation using the Allure Framework:
To generate the report using the Allure Framework, we will first install the Newman-Reporter-Allure-Reporter library:

```
npm install -g newman-reporter-allure
```

```
newman run collection.json -r allure
```

# Augmenting the API with other endpoints using JSON Server:
Let's create a db.json file with new endpoints to simulate the Restful-booker API using JSON Server:

```
{
  "bookings": [],
  "transportReservations": []
}
```

# Adding JSON Server to the Automation Project Repository:
We can include the db.json and the JSON Server initialization script in the project repository.
