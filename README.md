 Hall Booking API 


 1. Overview :    
     
      -  This project is a simple Hall Booking Application API built using Node.js and Express.js. It allows users to:

      -  Create Rooms with specific details like number of seats, amenities, and price per hour.

      -  Book Rooms for a specific date and time, ensuring that rooms are not double-booked

 
 2. Features :

     - Room Management :

         Create rooms with attributes such as the number of seats, amenities, and price per hour.
    
     - Booking System :

         Allows customers to book rooms for specific dates and times. Prevents double-booking of rooms.

     - View Room Booking Data :

         List all rooms with their booking details, including customer name, booking status, and time slots.

     - View Customer Booking Data :

         List all customers along with their booking history, including room name, date, start time, and end time.
        
     - Customer Booking Frequency :

         Show how many times a customer has booked rooms and the details of each booking.


 
   3. API Endpoints :
 
      Create Room  : POST /api/rooms/create

        - Body Parameters  :

             name: Name of the room

             seats: Number of seats

             amenities: List of amenities

             pricePerHour: Price per hour for the room

        - Response  :  JSON of the newly created room.

 
      Book a Room  : POST /api/bookings/create

        - Body Parameters  :
  
             customerName: Name of the customer booking the room

             date: Date of the booking

             startTime: Start time of the booking

             endTime: End time of the booking

             roomId: ID of the room to be booked

        - Response :  JSON of the booking details or error if room is already booked for that time.


      List All Rooms with Booked Data  : GET /api/rooms/booked

        - Response :  JSON array of rooms with booking details (room name, booked status, customer name, date, start time, end time).

     
      List All Customers with Booking Data : GET /api/bookings/customers

        - Response : JSON array of customers with their booking history (customer name, room name, date, start time, end time).


      Count Customer Bookings : GET /api/bookings/customer/:customerName

         - Response :  JSON with total number of bookings by the customer and booking details.

   4. Basic Validation Rules :

         -  Room booking is restricted if the room is already booked for the same date and overlapping time period.

         -  Proper error messages are returned for invalid room IDs or customer names.


   5. Setup Instruction  :

         -  The server will run at http://localhost:3000.

         -  API Testing You can use tools like Postman to test the API.

   6. License:

         -   This project is licensed under the MIT License.
