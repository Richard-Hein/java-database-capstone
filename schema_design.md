
# Section 1: Architecture summary

This Spring Boot application uses both MVC and REST controllers. Thymeleaf templates are used for the Admin and Doctor dashboards, while REST APIs serve all other modules. The application interacts with two databases—MySQL (for patient, doctor, appointment, and admin data) and MongoDB (for prescriptions). All controllers route requests through a common service layer, which in turn delegates to the appropriate repositories. MySQL uses JPA entities while MongoDB uses document models.

# Section 2: Numbered flow of data and control

1. User accesses AdminDashboard or Appointment pages. ( User Interface Layer )
2. The action is routed to the appropriate Thymeleaf or REST controller. ( Controller Layer )
3. The controller calls the service layer. ( Service Layer )
4. Service layer communicate with repository layer for data access operation. ( Repository Layer )
5. Repositories interface directly with the underlying database engine. ( Database Access )
6. Data retreived from  the database is mapped into Java model class. ( Model Binding )
7. The model are passed form the controller to Thymeleaf or serialized into JSON depeneding on the Customer. (Application Layer )
