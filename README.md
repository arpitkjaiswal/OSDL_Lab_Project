# OSDL_Lab_Project\
//  product promt
Create a FAANG level Hotel Management Application using JavaFX.

Project goals
- Build a standalone JavaFX desktop application that is production quality, modular, and well documented.
- Follow clean architecture and SOLID principles.
- No external database. Use in-memory models with optional file persistence using JSON.
- Provide a polished, accessible, and responsive UI with CSS theming.

Technical stack
- Java 17 or later.
- JavaFX 17 or later.
- Build with Maven or Gradle. Provide both build files if feasible.
- Use Jackson or Gson for JSON serialization.
- Use JUnit 5 for unit tests and TestFX for UI tests.
- Provide a simple CI configuration for GitHub Actions that runs build and tests.

High level features
1. Room management
- Add, edit, delete, and view rooms.
- Room fields: **roomNumber**, **roomType** (Single, Double, Suite), **pricePerNight**, **status** (Available, Booked, Maintenance), **description**, **amenities**.
- Table view with sorting, column filtering, and search by room number and type.

2. Booking flow
- Book available rooms with customer details: **name**, **contactNumber**, **email**, **checkInDate**, **expectedCheckOutDate**.
- Validate input and show inline errors.
- Prevent double booking and show conflict warnings.
- Persist bookings in memory and to JSON file.

3. Checkout flow
- Checkout a booked room, calculate bill using nights stayed and price per night.
- Support manual adjustments and taxes.
- Mark room as Available and archive booking to a history file.

4. Persistence and sample data
- Save and load rooms and bookings to JSON files on startup and shutdown.
- Provide sample data loader for demo mode.
- Implement a FileHandler class with robust error handling and atomic writes.

5. UI and UX
- Tab based layout with tabs: **Dashboard**, **Rooms**, **Bookings**, **Checkout**, **Reports**, **Settings**.
- Dashboard shows KPIs: occupancy rate, revenue today, upcoming checkouts.
- Use responsive layouts with VBox HBox GridPane and CSS for a modern theme.
- Provide a light and dark theme toggle.
- Add accessible labels, keyboard navigation, and readable color contrast.

6. Architecture and code quality
- Use MVC or MVVM pattern with clear separation of UI, domain, and persistence.
- Create domain classes: **Room**, **Customer**, **Booking**, **Invoice**.
- Create services: **RoomService**, **BookingService**, **BillingService**, **FileService**.
- Use interfaces for services and dependency injection via constructors.
- Add logging with SLF4J and a simple file logger.
- Add input validation utilities and custom exceptions.

7. Testing and CI
- Unit tests for services and domain logic with JUnit 5.
- Integration tests for file persistence.
- UI tests for core flows using TestFX.
- GitHub Actions workflow that runs `mvn test` or `gradle test` and builds the app.

8. Packaging and run instructions
- Provide a runnable fat jar and a native launcher script for Windows Mac and Linux.
- Include instructions to run with `java -jar` and how to build with Maven or Gradle.

9. Documentation and deliverables
- Provide a README with project overview, architecture diagram, build and run steps, sample screenshots, and contribution guidelines.
- Provide inline Javadoc for public classes and methods.
- Provide sample unit test reports and code coverage instructions.

Non functional requirements
- Handle concurrency for booking operations to avoid race conditions.
- Validate all user input and show friendly error messages.
- Keep UI responsive by using background threads for IO.
- Keep code modular and ready for extension such as adding payments or multi user roles.

Extra polish
- Add export to CSV for bookings and invoices.
- Add simple reporting: revenue by date range and occupancy chart.
- Add keyboard shortcuts for common actions.
- Provide sample commit messages and a suggested Git branching strategy.

Deliverables
- Complete source code in a standard Maven or Gradle layout.
- Build files and GitHub Actions workflow.
- README and architecture diagram.
- Sample data JSON files.
- Unit tests and UI tests.
- Runnable jar and platform launcher scripts.

Quality expectations
- Clean, idiomatic Java code with meaningful names and comments.
- Small, focused classes and methods.
- No hard coded strings in UI; use a resource bundle for labels.
- Provide clear TODOs where future improvements belong.
