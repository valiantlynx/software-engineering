### **Step 1: Create the Use Case Diagram (Top-Down Overview)**
- **Actors**:
  - **Patient**:
    - **Register Patient**
    - **Login Patient**
    - **Schedule Appointment**
    - **View Medical Records**
    - **Make Payment**
  - **Doctor**:
    - **Login Doctor**
    - **View Patient Records**
    - **Update Patient Records**
    - **Manage Appointments**
  - **Administrator**:
    - **Login Administrator**
    - **Manage Staff**
    - **Manage Hospital Resources**
    - **Generate Reports**
    - **Process Billing**
    - **Send Notifications**

- **Use Cases**:
  - **Register Patient**: Patient registers by providing personal and health insurance information.
  - **Login User**: Patient, Doctor, and Administrator log in with credentials.
  - **Schedule Appointment**: Patient schedules an appointment with available doctors.
  - **View Medical Records**: Patient views their medical records, while the doctor views patient records.
  - **Update Medical Records**: Doctor updates patient treatment details.
  - **Process Payment**: Patient makes payments for hospital services.
  - **Send Notification**: System sends appointment reminders and alerts.
  - **Manage Staff**: Administrator manages hospital staff details.
  - **Manage Hospital Resources**: Administrator manages equipment, rooms, and other resources.
  - **Generate Report**: Administrator generates reports for hospital management.
  - **Process Billing**: Administrator processes bills for patients.


### **Step 2: Use Case/Requirements Matrix**
- Create a matrix where each use case is mapped to the relevant functional requirements from the SRS document.
  
| **Use Case**                  | **Functional Requirements**                       |
|-------------------------------|---------------------------------------------------|
| **Register Patient**          | FR1 (Register patient), FR2 (Login patient), FR3 (Password recovery) |
| **Login User**                | FR2 (Login patient), FR4 (Login doctor/admin)     |
| **Schedule Appointment**      | FR4 (View available doctors), FR5 (Schedule appointments), FR6 (Receive confirmation) |
| **View Medical Records**      | FR7 (Access EMR), FR9 (Patient read-only access)  |
| **Update Medical Records**    | FR8 (Update patient details)                      |
| **Process Payment**           | FR10 (Generate bill), FR11 (Make payment online), FR12 (Receive receipt) |
| **Send Notification**         | FR16 (Send reminders), FR17 (Alert resource shortage) |
| **Manage Staff**              | FR13 (Manage doctor and staff profiles)           |
| **Manage Hospital Resources** | FR14 (Manage resources)                           |
| **Generate Report**           | FR14 (Access hospital reports and analytics)      |
| **Process Billing**           | FR15 (Manage billing and payment information)     |


### **Step 3: Simple UI Mock-Ups for Each Use Case**
For each use case, create a simple user interface mock-up that helps visualize how the user interacts with the system.

#### **UI for Register Patient**:
- **Elements**:
  - **Form Fields**: Full name, email, password, contact number, address, health insurance details.
  - **Buttons**: "Register".
  - **Other Elements**: Terms and conditions checkbox.
  
#### **UI for Login User**:
- **Elements**:
  - **Form Fields**: Email, password.
  - **Buttons**: "Login", "Forgot Password".
  
#### **UI for Schedule Appointment**:
- **Elements**:
  - **Dropdown**: Select doctor’s specialty.
  - **Calendar View**: Available slots to choose from.
  - **Buttons**: "Confirm Appointment".
  
#### **UI for View Medical Records**:
- **Elements**:
  - **List View**: Displays past consultations, lab results, prescriptions.
  - **Read-Only Fields**: Display patient records.
  
#### **UI for Update Medical Records**:
- **Elements**:
  - **Editable Fields**: Patient information like diagnosis, treatment.
  - **Buttons**: "Save Changes".
  
#### **UI for Process Payment**:
- **Elements**:
  - **Bill Summary Section**: Details of charges.
  - **Payment Information Fields**: Card number, expiry, CVV.
  - **Buttons**: "Make Payment".
  
#### **UI for Manage Staff**:
- **Elements**:
  - **List View**: Displays staff members.
  - **Buttons**: "Add Staff", "Edit", "Delete".

#### **UI for Manage Hospital Resources**:
- **Elements**:
  - **Dashboard**: List of resources.
  - **Buttons**: "Add Resource", "Edit Resource".

#### **UI for Generate Report**:
- **Elements**:
  - **Select Report Type**: Dropdown.
  - **Date Range**: Start and end date.
  - **Buttons**: "Generate Report".

#### **UI for Send Notification**:
- **Elements**:
  - **Recipient List**: Patients, doctors.
  - **Message Input Box**: Text area for entering notification content.
  - **Buttons**: "Send Notification".
  

### **Step 4: Interaction Diagrams for Each Use Case (Three Levels)**

#### **Use Case: Register Patient**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Patient
- **Action**: Patient registers for an account.
- **System Interaction**: System saves patient information.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Patient** enters personal details, email, and password.
2. **System** validates information.
3. **System** creates a new patient profile and stores it.
4. **System** confirms registration by displaying a success message.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Patient** enters personal information, email, password, and health insurance details.
2. **System** validates if the email is unique and checks for proper input format.
3. **System** interacts with the **Database** to store patient details.
4. **System** sends a registration confirmation email using the **Notification Service**.
5. **System** displays confirmation message to the patient.

#### **Use Case: Login User**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Patient, Doctor, Administrator
- **Action**: Actor logs in to the system.
- **System Interaction**: System validates credentials and grants access.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Actor** enters username and password.
2. **System** validates credentials.
3. **System** grants access if credentials are correct.
4. **System** displays appropriate dashboard based on the user role (Patient, Doctor, or Administrator).

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Actor** inputs username and password.
2. **System** checks credentials against the **User Database**.
3. If credentials match:
   - **System** creates a session for the user.
   - **System** interacts with the **Role Management Module** to determine the actor's role.
   - **System** loads the appropriate dashboard (patient, doctor, or admin).
4. If credentials do not match:
   - **System** displays an error message and allows the actor to try again.

#### **Use Case: Schedule Appointment**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Patient
- **Action**: Patient schedules an appointment.
- **System Interaction**: System confirms the appointment.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Patient** views list of available doctors.
2. **Patient** selects doctor and appointment slot.
3. **System** confirms the appointment.
4. **System** sends appointment confirmation to the patient.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Patient** logs in and requests to schedule an appointment.
2. **System** retrieves doctor availability from the **Appointment Management System**.
3. **Patient** selects preferred doctor and time slot.
4. **System** interacts with the **Database** to book the appointment.
5. **System** sends appointment confirmation to the **Notification Service**.
6. **Notification Service** sends an email and SMS to the patient.

#### **Use Case: View Medical Records**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Patient, Doctor
- **Action**: Patient or Doctor views medical records.
- **System Interaction**: System retrieves and displays medical records.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Actor** requests to view medical records.
2. **System** retrieves records from the database.
3. **System** displays the medical records to the actor.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Actor** logs in and selects the "View Medical Records" option.
2. **System** retrieves **MedicalRecord** from the **Database** based on `patientID`.
3. **System** verifies access rights:
   - If **Patient**, only read access is granted.
   - If **Doctor**, full access is granted.
4. **System** displays the records to the actor with appropriate access rights.

#### **Use Case: Update Medical Records**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Doctor
- **Action**: Doctor updates patient medical records.
- **System Interaction**: System saves updated medical records.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Doctor** views patient medical records.
2. **Doctor** makes updates to patient diagnosis or prescription.
3. **System** saves the updated medical records.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Doctor** logs in and selects a patient to update records.
2. **System** retrieves **MedicalRecord** from the **Database** based on `patientID`.
3. **Doctor** updates diagnosis or prescription information.
4. **System** validates the data and saves it to the **Database**.
5. **System** notifies the **Patient** via **Notification Service** that their records have been updated.

#### **Use Case: Process Payment**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Patient
- **Action**: Patient makes a payment.
- **System Interaction**: System processes the payment.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Patient** views billing details.
2. **Patient** selects payment method and submits payment.
3. **System** processes payment and generates a receipt.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Patient** logs in and selects "View Billing Details."
2. **System** retrieves outstanding bills from the **Billing Module**.
3. **Patient** enters payment information.
4. **System** interacts with **Payment Gateway** to process the payment.
5. If successful:
   - **System** updates the **Billing Module** with payment status.
   - **System** sends a receipt to **Notification Service** for email delivery to the patient.
6. If unsuccessful:
   - **System** notifies the patient of payment failure.

#### **Use Case: Manage Staff**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Administrator
- **Action**: Administrator manages staff details.
- **System Interaction**: System saves updated staff information.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Administrator** adds or updates staff information.
2. **System** saves the information to the database.
3. **System** confirms changes.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Administrator** logs in and selects the "Manage Staff" option.
2. **Administrator** adds or edits details for a staff member.
3. **System** validates the input data.
4. **System** updates **Staff Database** with the new or edited information.
5. **System** confirms success and logs the changes.

#### **Use Case: Manage Hospital Resources**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Administrator
- **Action**: Administrator manages hospital resources.
- **System Interaction**: System updates resource inventory.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Administrator** selects resource management.
2. **Administrator** adds or updates resource information.
3. **System** updates the resource database.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Administrator** logs in and selects "Manage Resources."
2. **System** retrieves current resources from the **Resource Database**.
3. **Administrator** adds a new resource or updates an existing one.
4. **System** validates and saves the changes to the **Resource Database**.
5. **System** confirms the update to the administrator.

#### **Use Case: Generate Report**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Administrator
- **Action**: Administrator generates a report.
- **System Interaction**: System produces the report.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Administrator** selects report type and parameters.
2. **System** compiles report data.
3. **System** generates and displays the report.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Administrator** logs in and selects "Generate Report."
2. **System** prompts for report type and parameters (e.g., date range).
3. **Administrator** inputs parameters.
4. **System** retrieves data from the **Database** based on input parameters.
5. **System** compiles data and generates the report.
6. **System** displays or exports the report as requested.

#### **Use Case: Send Notification**
##### **Level 0 Interaction Diagram (High-Level Overview)**
- **Actors Involved**: Administrator
- **Action**: Administrator sends a notification.
- **System Interaction**: System delivers the notification.

##### **Level 1 Interaction Diagram (Key Actions)**
1. **Administrator** selects recipients for the notification.
2. **Administrator** drafts the notification message.
3. **System** sends the notification.

##### **Level 2 Interaction Diagram (Detailed System Processes)**
1. **Administrator** logs in and selects "Send Notification."
2. **Administrator** selects recipients (patients or doctors).
3. **Administrator** drafts and confirms the message.
4. **System** interacts with the **Notification Service** to send emails and SMS.
5. **Notification Service** delivers the notification to selected recipients.
6. **System** confirms notification delivery to the administrator.

These detailed interaction diagrams provide comprehensive coverage of how each use case interacts with the system at different levels of complexity, from a high-level overview to deep system-level interactions. This ensures you understand every aspect of the user interactions with the system, backend processes, and third-party integrations for each use case.**.


### **Step 5: Class Diagram for Each Use Case**

#### **Use Case: Register Patient**
- **Classes**:
  - **Patient**:
    - **Attributes**: 
      - `patientID: int`
      - `name: str`
      - `email: str`
      - `contactDetails: str`
      - `insuranceDetails: str`
    - **Methods**: 
      - `register(): void` — Registers a new patient in the system.
  - **UserManager**:
    - **Attributes**: None
    - **Methods**: 
      - `createUser(patient: Patient): bool` — Creates a new user profile in the system.
      - `validateRegistration(email: str): bool` — Validates if the email is unique.

#### **Use Case: Login User**
- **Classes**:
  - **User** (Base Class for all users - `Patient`, `Doctor`, `Administrator`):
    - **Attributes**: 
      - `userID: int`
      - `username: str`
      - `password: str`
    - **Methods**: 
      - `login(username: str, password: str): bool` — Validates credentials and logs in the user.
  - **SessionManager**:
    - **Attributes**:
      - `activeSessions: list<Session>`
    - **Methods**:
      - `createSession(user: User): Session` — Creates a new session after successful login.
      - `validateSession(sessionID: int): bool` — Validates if the session is active.

#### **Use Case: Schedule Appointment**
- **Classes**:
  - **Patient**:
    - **Attributes**: 
      - `patientID: int`
      - `name: str`
      - `email: str`
    - **Methods**: 
      - `scheduleAppointment(doctorID: int, date: str, time: str): Appointment` — Schedules a new appointment.
  - **Doctor**:
    - **Attributes**: 
      - `doctorID: int`
      - `specialty: str`
      - `availability: list<TimeSlot>`
    - **Methods**: 
      - `viewAvailability(): list<TimeSlot>` — Views available slots for appointments.
  - **Appointment**:
    - **Attributes**: 
      - `appointmentID: int`
      - `date: str`
      - `time: str`
      - `patientID: int`
      - `doctorID: int`
    - **Methods**: 
      - `confirmAppointment(): bool` — Confirms the appointment.

#### **Use Case: View Medical Records**
- **Classes**:
  - **Patient**:
    - **Methods**: 
      - `viewMedicalRecords(patientID: int): MedicalRecord` — Allows a patient to view their medical records.
  - **Doctor**:
    - **Methods**:
      - `viewPatientRecords(patientID: int): MedicalRecord` — Allows a doctor to view a patient’s medical records.
  - **MedicalRecord**:
    - **Attributes**: 
      - `recordID: int`
      - `patientID: int`
      - `details: str`
      - `testResults: list<TestResult>`
      - `prescriptions: list<Prescription>`
    - **Methods**: 
      - `getRecord(patientID: int): MedicalRecord` — Retrieves a patient’s medical record.

#### **Use Case: Update Medical Records**
- **Classes**:
  - **Doctor**:
    - **Methods**: 
      - `updateMedicalRecord(patientID: int, updates: str): bool` — Updates a patient’s medical record.
  - **MedicalRecord**:
    - **Attributes**: 
      - `recordID: int`
      - `patientID: int`
      - `details: str`
      - `testResults: list<TestResult>`
      - `prescriptions: list<Prescription>`
    - **Methods**: 
      - `updateDetails(updates: str): void` — Applies updates to the patient record.

#### **Use Case: Process Payment**
- **Classes**:
  - **Billing**:
    - **Attributes**: 
      - `billID: int`
      - `patientID: int`
      - `amount: float`
      - `services: list<Service>`
    - **Methods**: 
      - `generateBill(patientID: int, services: list<Service>): Billing` — Generates a bill for the patient.
  - **Payment**:
    - **Attributes**: 
      - `paymentID: int`
      - `billID: int`
      - `amount: float`
      - `method: str`
      - `status: str`
    - **Methods**: 
      - `processPayment(paymentDetails: Payment): bool` — Processes payment using the provided details.
  - **PaymentGateway**:
    - **Attributes**: None
    - **Methods**: 
      - `authorizePayment(payment: Payment): bool` — Authorizes the payment using an external payment service.
  
#### **Use Case: Manage Staff**
- **Classes**:
  - **Administrator**:
    - **Methods**: 
      - `addStaff(staff: Staff): bool` — Adds a new staff member.
      - `updateStaff(staffID: int, details: str): bool` — Updates an existing staff member’s information.
      - `removeStaff(staffID: int): bool` — Removes a staff member.
  - **Staff**:
    - **Attributes**: 
      - `staffID: int`
      - `name: str`
      - `role: str`
      - `contactDetails: str`
    - **Methods**: None
  
#### **Use Case: Manage Hospital Resources**
- **Classes**:
  - **Administrator**:
    - **Methods**: 
      - `addResource(resource: Resource): bool` — Adds a new hospital resource.
      - `updateResource(resourceID: int, details: str): bool` — Updates an existing hospital resource.
  - **Resource**:
    - **Attributes**: 
      - `resourceID: int`
      - `name: str`
      - `quantity: int`
      - `location: str`
    - **Methods**: None

#### **Use Case: Generate Report**
- **Classes**:
  - **Administrator**:
    - **Methods**: 
      - `generateReport(reportType: str, parameters: dict): Report` — Generates different types of hospital reports.
  - **Report**:
    - **Attributes**: 
      - `reportID: int`
      - `type: str`
      - `content: str`
    - **Methods**: 
      - `exportReport(format: str): void` — Exports the report in the specified format.

#### **Use Case: Send Notification**
- **Classes**:
  - **NotificationService**:
    - **Attributes**: 
      - `notificationID: int`
      - `recipientID: int`
      - `message: str`
      - `type: str`
    - **Methods**: 
      - `sendNotification(recipientID: int, message: str, type: str): bool` — Sends a notification to the recipient (email or SMS).
  - **Administrator**:
    - **Methods**: 
      - `createNotification(recipientID: int, message: str, type: str): Notification` — Creates a new notification to be sent.

### **Class Relationships**
- **Patient**, **Doctor**, and **Administrator** all inherit from a base class **User** to handle common attributes like `userID`, `username`, and `password`.
- **Appointment** class is associated with both **Patient** and **Doctor** classes, representing the relationship between doctors and patients during an appointment.
- **MedicalRecord** is associated with both **Patient** and **Doctor**, where **Patient** has access to view, and **Doctor** has access to both view and update.
- **Billing** and **Payment** are closely related, where **Billing** generates bills, and **Payment** handles payments for those bills.
- **Staff** and **Resource** are managed by **Administrator** through actions such as add, update, and remove.
- **NotificationService** collaborates with **Administrator** to manage sending notifications to **Patient** or **Doctor**.


### **Step 6: Package Diagram for Related Classes**
Group classes into logical packages for better modularity and structure.
To ensure a modular and maintainable system, group the classes identified in the use cases into logical packages. This helps to segregate functionalities and keep similar features together, which in turn supports maintainability, reusability, and scalability.

Below is a **detailed breakdown** of how the classes are grouped into packages, including class descriptions and relationships.

#### **Packages Overview**
1. **User Management Package**
2. **Appointment Management Package**
3. **Billing Package**
4. **Medical Record Package**
5. **Notification Package**
6. **Resource Management Package**
7. **Staff Management Package**

### **1. User Management Package**
- **Purpose**: Handles user registration, login, and profile management for all actors (Patients, Doctors, Administrators).
- **Classes**:
  - **User**: Base class representing a generic user.
    - **Attributes**: `userID`, `username`, `password`
    - **Methods**: `login()`
  - **Patient**: Inherits from `User`.
    - **Attributes**: `patientID`, `name`, `contactDetails`, `insuranceDetails`
    - **Methods**: `register()`, `scheduleAppointment()`, `viewMedicalRecords()`
  - **Doctor**: Inherits from `User`.
    - **Attributes**: `doctorID`, `specialty`, `availability`
    - **Methods**: `viewPatientRecords()`, `updateMedicalRecord()`
  - **Administrator**: Inherits from `User`.
    - **Attributes**: `adminID`, `role`
    - **Methods**: `manageStaff()`, `manageResources()`, `generateReport()`

### **2. Appointment Management Package**
- **Purpose**: Manages all activities related to appointment scheduling, updating, and confirmation.
- **Classes**:
  - **Appointment**:
    - **Attributes**: `appointmentID`, `date`, `time`, `patientID`, `doctorID`
    - **Methods**: `confirmAppointment()`
  - **Schedule**:
    - **Attributes**: `doctorID`, `availableSlots`
    - **Methods**: `viewAvailability()`

### **3. Billing Package**
- **Purpose**: Handles billing and payment processing, including integration with external payment gateways.
- **Classes**:
  - **Billing**:
    - **Attributes**: `billID`, `patientID`, `amount`, `services`
    - **Methods**: `generateBill()`
  - **Payment**:
    - **Attributes**: `paymentID`, `billID`, `amount`, `method`, `status`
    - **Methods**: `processPayment()`
  - **PaymentGateway** (Optional/Abstract Interface):
    - **Methods**: `authorizePayment()`

### **4. Medical Record Package**
- **Purpose**: Manages access to and updates of electronic medical records.
- **Classes**:
  - **MedicalRecord**:
    - **Attributes**: `recordID`, `patientID`, `details`, `testResults`, `prescriptions`
    - **Methods**: `getRecord()`, `updateDetails()`
  - **TestResult**:
    - **Attributes**: `testID`, `result`, `date`
  - **Prescription**:
    - **Attributes**: `prescriptionID`, `medication`, `dosage`

### **5. Notification Package**
- **Purpose**: Handles notifications (such as reminders and alerts) for patients, doctors, and administrators.
- **Classes**:
  - **NotificationService**:
    - **Attributes**: `notificationID`, `recipientID`, `message`, `type`
    - **Methods**: `sendNotification()`
  - **NotificationLog**:
    - **Attributes**: `logID`, `notificationID`, `status`, `timestamp`
    - **Methods**: `logNotification()`

### **6. Resource Management Package**
- **Purpose**: Manages hospital resources such as rooms, equipment, and consumables.
- **Classes**:
  - **Resource**:
    - **Attributes**: `resourceID`, `name`, `quantity`, `location`
    - **Methods**: `addResource()`, `updateResource()`, `removeResource()`
  - **Administrator** (Shared with User Management):
    - **Methods**: `manageResources()`

### **7. Staff Management Package**
- **Purpose**: Handles hospital staff information, including adding, updating, and removing staff members.
- **Classes**:
  - **Staff**:
    - **Attributes**: `staffID`, `name`, `role`, `contactDetails`
  - **Administrator** (Shared with User Management):
    - **Methods**: `manageStaff()`

### **Package Relationships**
The following relationships exist between the packages:
- **User Management Package** interacts with the **Appointment Management Package** when the patient schedules or views an appointment.
- **User Management Package** interacts with the **Billing Package** for viewing and making payments.
- **Medical Record Package** is accessed by both **Patient** and **Doctor** classes from the **User Management Package**.
- **Notification Package** interacts with all other packages for sending notifications about appointments, billing, or resource alerts.
- **Administrator** in the **User Management Package** manages both **Resource Management Package** and **Staff Management Package**.

### **Package Diagram Summary**
To create the package diagram, visually represent these logical groups and relationships:
- **User Management** package is centrally connected, as it encompasses the different actors (`Patient`, `Doctor`, `Administrator`), who interact with the other packages.
- **Appointment Management** and **Billing** packages are separate modules that can be accessed through actions by patients.
- **Medical Record** package is accessed by both patients and doctors for managing patient health records.
- **Notification** package serves as a utility package, interacting with other packages to notify users about various events.
- **Resource Management** and **Staff Management** packages are managed exclusively by the **Administrator**.

### **Relationships Between Packages**
- **Dependency**: 
  - **Notification Package** depends on the **User Management**, **Appointment Management**, and **Billing** packages for getting the recipients of notifications.
  - **Billing Package** depends on the **Payment Gateway** for handling external payments.
- **Association**:
  - **Medical Record Package** is associated with both the **User Management Package** (through `Patient` and `Doctor`) to manage records.
- **Generalization**:
  - **User** serves as the base class for `Patient`, `Doctor`, and `Administrator`.

### **Package Diagram Visualization Guide**
- **Central Core (User Management)**: Place the **User Management** package in the center as the main package containing all actors.
- **Dependent Packages**:
  - **Appointment Management**, **Billing**, and **Medical Record** packages should be placed around the **User Management** package, with appropriate dependency arrows indicating which classes depend on which package.
- **Utility Packages**:
  - **Notification Package**: Positioned in a way that shows its interactions with other packages.
  - **Resource Management** and **Staff Management**: Connected to the **Administrator** within the **User Management Package**.

This detailed breakdown ensures that each functional module is well-encapsulated, with clearly defined relationships. This approach is modular and adheres to principles like **Single Responsibility** and **Open/Closed** for each package, making it easy to extend and maintain the system. 


### **Step 7: CRC Cards for Each Class**

A **CRC (Class-Responsibility-Collaborator) card** is a great way to understand the roles of classes in the system, what responsibilities they have, and which classes they interact with. Below are the detailed CRC cards for every class across all packages in the Hospital Management System.

#### **1. User Management Package**
##### **Class: User**
- **Responsibilities**:
  - Store common user attributes (username, password).
  - Provide login functionality for all users.
- **Collaborators**:
  - **SessionManager**: Manages active sessions for logged-in users.
- **Notes**:
  - This is a base class for `Patient`, `Doctor`, and `Administrator`.

##### **Class: Patient** (Inherits from `User`)
- **Responsibilities**:
  - Register for a patient account.
  - Schedule and manage appointments.
  - View medical records.
- **Collaborators**:
  - **Appointment**: Schedule and manage patient appointments.
  - **MedicalRecord**: Access patient’s medical records.
  - **Billing**: Manage billing and payment for services.
  - **NotificationService**: Receive reminders and alerts.
- **Notes**:
  - Has attributes such as `patientID`, `contactDetails`, and `insuranceDetails`.

##### **Class: Doctor** (Inherits from `User`)
- **Responsibilities**:
  - View and update patient records.
  - Manage patient appointments.
- **Collaborators**:
  - **MedicalRecord**: Update patient’s medical records.
  - **Appointment**: Manage appointment schedules.
- **Notes**:
  - The doctor class has specialty and availability attributes.

##### **Class: Administrator** (Inherits from `User`)
- **Responsibilities**:
  - Manage hospital resources.
  - Manage staff.
  - Generate reports.
- **Collaborators**:
  - **Resource**: Manage hospital resources.
  - **Staff**: Add, update, or remove staff.
  - **Report**: Generate hospital-related reports.
- **Notes**:
  - The administrator role also has the ability to send notifications.

##### **Class: SessionManager**
- **Responsibilities**:
  - Create and validate active user sessions.
  - Manage logout actions.
- **Collaborators**:
  - **User**: Create a session for users upon successful login.
- **Notes**:
  - Handles session expiration and security.

#### **2. Appointment Management Package**
##### **Class: Appointment**
- **Responsibilities**:
  - Store appointment details including patient and doctor information.
  - Confirm or modify appointment schedules.
- **Collaborators**:
  - **Patient**: Schedule appointments.
  - **Doctor**: Assign to appointments.
  - **NotificationService**: Notify patients and doctors about upcoming appointments.
- **Notes**:
  - This class also interacts with the `Schedule` class to book available time slots.

##### **Class: Schedule**
- **Responsibilities**:
  - Maintain the availability of doctors.
  - Retrieve available slots for booking.
- **Collaborators**:
  - **Doctor**: Obtain and update availability.
  - **Appointment**: Coordinate appointment scheduling.
- **Notes**:
  - Acts as a helper class to manage time slots.

#### **3. Billing Package**
##### **Class: Billing**
- **Responsibilities**:
  - Generate and manage billing information for patients.
  - Track services and treatments provided.
- **Collaborators**:
  - **Patient**: Generate bills for patient services.
  - **Payment**: Process payment for generated bills.
  - **PaymentGateway**: Integrate with external payment gateway to process payments.
- **Notes**:
  - Includes details like services provided and payment status.

##### **Class: Payment**
- **Responsibilities**:
  - Process payments for bills.
  - Validate payment details through the payment gateway.
- **Collaborators**:
  - **Billing**: Access bill details for processing.
  - **PaymentGateway**: Process payment securely.
- **Notes**:
  - Manages payment status (e.g., pending, successful).

##### **Class: PaymentGateway** (Interface)
- **Responsibilities**:
  - Authorize payments via external payment services.
- **Collaborators**:
  - **Payment**: Execute payment authorization.
- **Notes**:
  - Used for integration with third-party payment processing services.

#### **4. Medical Record Package**
##### **Class: MedicalRecord**
- **Responsibilities**:
  - Store patient medical information including diagnosis, treatment, and prescriptions.
  - Update and retrieve patient medical details.
- **Collaborators**:
  - **Patient**: Provide read-only access to the patient's own records.
  - **Doctor**: Allow full access to update records.
  - **NotificationService**: Notify patients when their records are updated.
- **Notes**:
  - Interacts with the `Prescription` and `TestResult` classes to maintain a comprehensive record.

##### **Class: TestResult**
- **Responsibilities**:
  - Store test results for patients.
  - Allow updates for new test results.
- **Collaborators**:
  - **MedicalRecord**: Add new test results to a patient’s record.
- **Notes**:
  - Each result is associated with a specific `MedicalRecord`.

##### **Class: Prescription**
- **Responsibilities**:
  - Store prescription details for patient medications.
- **Collaborators**:
  - **MedicalRecord**: Attach prescription to the medical record.
- **Notes**:
  - Tracks medication, dosage, and prescribing doctor.

#### **5. Notification Package**
##### **Class: NotificationService**
- **Responsibilities**:
  - Send email or SMS notifications to users.
  - Log notifications sent.
- **Collaborators**:
  - **Patient**, **Doctor**, **Administrator**: Send notifications based on various triggers (appointments, updates, alerts).
  - **NotificationLog**: Log details of each notification sent.
- **Notes**:
  - Supports different types of notifications (appointment reminders, updates, alerts).

##### **Class: NotificationLog**
- **Responsibilities**:
  - Log notifications for future reference and auditing.
- **Collaborators**:
  - **NotificationService**: Store logs for each notification sent.
- **Notes**:
  - Stores log details such as notification type, recipient, timestamp, and status.

#### **6. Resource Management Package**
##### **Class: Resource**
- **Responsibilities**:
  - Manage hospital resources such as equipment, rooms, and inventory.
  - Allow addition, update, or removal of resources.
- **Collaborators**:
  - **Administrator**: Manage resource details.
- **Notes**:
  - Keeps track of available quantity and resource status.

##### **Class: Administrator** (from User Management)
- **Responsibilities**:
  - Manage hospital resources.
- **Collaborators**:
  - **Resource**: Adds, updates, and manages resource allocation.
- **Notes**:
  - Shared with User Management and interacts with other packages.

#### **7. Staff Management Package**
##### **Class: Staff**
- **Responsibilities**:
  - Store details of staff members (nurses, technicians, etc.).
- **Collaborators**:
  - **Administrator**: Add, update, and remove staff members.
- **Notes**:
  - Has attributes like `staffID`, `role`, and `contactDetails`.

##### **Class: Administrator** (from User Management)
- **Responsibilities**:
  - Manage hospital staff.
- **Collaborators**:
  - **Staff**: Adds or updates staff information.
- **Notes**:
  - Shared class, interacts with other packages for holistic administration.

### **Summary of CRC Cards**
- Each **class** has a well-defined **responsibility** that contributes to a cohesive and functional system.
- **Collaborators** highlight how classes work together to fulfill specific system features or use cases.
- The **responsibility** for each class follows the **Single Responsibility Principle** to ensure that every class has a focused role in the system.

These CRC cards provide a comprehensive view of each class in the system, detailing not only what each class does but also how it interacts with other parts of the system. This will be useful when designing the overall system architecture and ensuring that all parts fit together in a well-defined, modular fashion. 


### **Step 8: Documenting the Use of SOLID Principles**
In Step 8, we document how **SOLID principles** have been incorporated into the system design to ensure modularity, maintainability, and scalability. Below, I will describe how each principle has been applied across the classes and packages designed in the previous steps.

#### **S - Single Responsibility Principle (SRP)**
**SRP** states that each class should have only one reason to change, meaning that it should only have one responsibility. Here's how SRP is applied throughout the system:

- **User Management**:
  - The **User** class is responsible only for storing common attributes and handling login functionality. Specialized classes like **Patient**, **Doctor**, and **Administrator** extend **User** and have unique responsibilities specific to their roles.
  - The **SessionManager** is solely responsible for managing user sessions, including creating and validating them.
- **Medical Record Management**:
  - The **MedicalRecord** class handles storing and updating patient medical data.
  - Separate classes like **Prescription** and **TestResult** are used to manage specific types of medical information, ensuring that **MedicalRecord** does not grow overly complex.
- **Billing and Payments**:
  - The **Billing** class is responsible for generating and storing billing information, while the **Payment** class handles the payment process itself.
  - The **PaymentGateway** interface abstracts external payment processing.
  
By adhering to SRP, the system ensures that each class is easy to understand and maintain, reducing the risk of changes affecting unrelated functionality.

#### **O - Open/Closed Principle (OCP)**
**OCP** states that classes should be open for extension but closed for modification. This means we should be able to add new functionality without changing existing code.

- **NotificationService**:
  - The **NotificationService** class is designed to be easily extended to add new notification methods (e.g., email, SMS, push notifications). If a new notification type is added, it can be done by extending the notification mechanism, rather than modifying the existing code.
- **User Roles**:
  - The **User** class is a base class that is extended by **Patient**, **Doctor**, and **Administrator**. New roles can be added by creating new subclasses without modifying the **User** class itself.
- **Appointment Scheduling**:
  - The **Schedule** class can be extended to include new appointment-related functionalities (e.g., rescheduling, appointment reminders) without modifying the core functionality.

By adhering to OCP, the system supports adding new features or extending existing ones without risking regression in existing features, thereby maintaining stability.

#### **L - Liskov Substitution Principle (LSP)**
**LSP** states that derived classes must be substitutable for their base classes without affecting the correctness of the program. Here's how LSP is applied:

- **User Subclasses**:
  - The **Patient**, **Doctor**, and **Administrator** classes all inherit from **User** and can be used in any context where **User** is expected. Each derived class extends the **User** class without changing its behavior.
- **NotificationService**:
  - If we have derived classes such as **EmailNotificationService** and **SMSNotificationService**, they can be used interchangeably in place of **NotificationService** wherever needed, ensuring consistent behavior.

By applying LSP, the system ensures that common behavior is preserved across related classes, preventing unexpected issues when substituting derived classes.

#### **I - Interface Segregation Principle (ISP)**
**ISP** states that no client should be forced to depend on methods it does not use. This means creating specific, small interfaces for different functionalities rather than one large general-purpose interface.

- **Payment Gateway**:
  - **PaymentGateway** is an interface that includes only the methods required for processing payments (`authorizePayment()`). Different payment processors can implement this interface according to their requirements without being forced to include unrelated methods.
- **Schedulable Interface**:
  - A **Schedulable** interface could be created for classes like **Patient** and **Doctor** that need scheduling capabilities. This way, other classes that do not need scheduling do not have to implement irrelevant methods.
  
By following ISP, the system ensures that classes are not burdened with methods they do not need, resulting in simpler, more focused class designs.

#### **D - Dependency Inversion Principle (DIP)**
**DIP** states that high-level modules should not depend on low-level modules. Both should depend on abstractions. This reduces the coupling between high-level and low-level modules.

- **PaymentGateway Interface**:
  - The **Payment** class depends on the **PaymentGateway** interface, rather than a specific payment processor implementation. This allows for different payment processors to be integrated without modifying the **Payment** class, thereby ensuring that the **Payment** class is independent of the implementation details of any specific payment processor.
- **NotificationService**:
  - **NotificationService** depends on an abstract mechanism for sending notifications rather than a specific method. This allows new notification channels to be integrated without modifying the core **NotificationService** logic.

By adhering to DIP, the system is more flexible and maintainable, as it is easier to replace or update components without affecting other parts of the system.

### **Summary of Applying SOLID Principles**
- **Single Responsibility Principle (SRP)**: Each class has a clear, distinct responsibility. This ensures the system is easy to understand and maintain.
- **Open/Closed Principle (OCP)**: Classes are open for extension but closed for modification, allowing new features to be added without altering existing code.
- **Liskov Substitution Principle (LSP)**: Subclasses can be substituted for their base classes without affecting the correctness of the application.
- **Interface Segregation Principle (ISP)**: Specific, small interfaces are used, ensuring that classes are not forced to implement methods they do not need.
- **Dependency Inversion Principle (DIP)**: High-level modules do not depend on low-level implementations. Instead, both depend on abstractions, making the system more flexible and easier to maintain.

By documenting and incorporating these principles, the system is designed with flexibility, scalability, and maintainability in mind, ensuring that future changes can be implemented with minimal disruption to existing features. This approach also promotes clean code practices, reduces technical debt, and provides a solid foundation for future growth and enhancements.


---
### **Step 9: Compile Everything into a Single PDF**
### **Structure of the PDF Document**
The document should include all the previous steps in a logical, easy-to-understand format. Here's the recommended structure, including specific sections, sub-sections, and content from Steps 1 to 8:

#### **1. Cover Page**
- **Title**: "Hospital Management System Design Documentation"
- **Subtitle**: "Use Case Analysis, Class Design, and Application of SOLID Principles"
- **Author**: Include your name and role.
- **Date**: Date of submission.
- **Version**: Version number of the document (e.g., Version 1.0).

#### **2. Table of Contents**
- This section helps the reader easily navigate through the document.
- Include:
  - Step 1: Use Case Diagram
  - Step 2: Use Case/Requirements Matrix
  - Step 3: UI Mock-Ups for Each Use Case
  - Step 4: Interaction Diagrams (Levels 0, 1, 2)
  - Step 5: Class Diagrams for Each Use Case
  - Step 6: Package Diagram
  - Step 7: CRC Cards for Each Class
  - Step 8: Application of SOLID Principles
  - Conclusion

#### **3. Use Case Diagram (Step 1)**
- **Overview**: Brief introduction explaining the importance of use case diagrams in visualizing system requirements.
- **Diagram**: Insert the **use case diagram** showing all the actors (`Patient`, `Doctor`, `Administrator`) and use cases.
- **Description of Actors and Use Cases**:
  - Detailed descriptions for all actors and each use case, as previously outlined.

#### **4. Use Case/Requirements Matrix (Step 2)**
- **Overview**: Explain how each use case is mapped to functional requirements.
- **Matrix**: Insert the matrix as a table with columns for **Use Case** and **Functional Requirements**. This will help readers understand how each requirement is fulfilled by a corresponding use case.

#### **5. UI Mock-Ups for Each Use Case (Step 3)**
- **Overview**: Include a brief paragraph on the role of user interfaces in ensuring a positive user experience.
- **Mock-Ups**:
  - For each use case, include a visual representation (a simple mock-up or wireframe).
  - **Explanation**: Accompany each UI mock-up with a brief explanation of what each field, button, or element does.
  - **Tools to Create Mock-Ups**: Use tools like Balsamiq, Figma, or even sketches. Ensure that these are clear, consistent, and user-friendly.

#### **6. Interaction Diagrams (Step 4)**
- **Overview**: Describe the purpose of interaction diagrams and how they help in understanding system processes.
- **Diagrams for Each Use Case**:
  - Include **Level 0, Level 1, and Level 2 Interaction Diagrams** for each use case.
  - **Use Case-wise Subsections**:
    - Register Patient
    - Login User
    - Schedule Appointment
    - View Medical Records
    - Update Medical Records
    - Process Payment
    - Manage Staff
    - Manage Hospital Resources
    - Generate Report
    - Send Notification
  - **Diagrams**: Ensure each interaction diagram is well-labeled and easy to understand.
  - **Narrative Descriptions**: Provide a step-by-step narrative of each interaction, as described in Step 4.

#### **7. Class Diagrams for Each Use Case (Step 5)**
- **Overview**: Explain how the class diagrams represent the structure and relationships between the system’s components.
- **Class Diagrams for Each Use Case**:
  - Insert the **class diagrams** for each use case (`Register Patient`, `Login User`, `Schedule Appointment`, etc.).
  - **Class Details**:
    - Include each class with **attributes, methods**, and **relationships**.
    - Explain how the **Single Responsibility Principle** is ensured in each class.
  - **Class Relationships**: Explain the relationships (association, inheritance, etc.) between the classes.

#### **8. Package Diagram (Step 6)**
- **Overview**: Describe how grouping classes into logical packages helps maintain modularity and ease of maintenance.
- **Package Diagram**:
  - Insert the **package diagram** that includes the logical grouping of classes (`User Management`, `Appointment Management`, `Billing`, etc.).
  - **Descriptions of Packages**:
    - Describe each package, including the classes it contains and their relationships.
  - **Package Interactions**: Explain how different packages interact and depend on each other.

#### **9. CRC Cards for Each Class (Step 7)**
- **Overview**: Describe the role of **CRC Cards** (Class, Responsibility, Collaborator) in the design process.
- **CRC Cards for All Classes**:
  - Include **CRC Cards** for each class (`User`, `Patient`, `Doctor`, `Administrator`, `Appointment`, etc.).
  - **Card Layout**: For each class, include:
    - **Class Name**: Title.
    - **Responsibilities**: A bullet-point list of the class’s responsibilities.
    - **Collaborators**: The classes with which it interacts.

#### **10. Application of SOLID Principles (Step 8)**
- **Overview**: Explain the importance of the **SOLID Principles** in software development, focusing on modularity, maintainability, and scalability.
- **How SOLID Principles Were Applied**:
  - **Single Responsibility Principle (SRP)**: Explain how each class has a well-defined responsibility.
  - **Open/Closed Principle (OCP)**: Provide examples of how classes were designed to be extendable without modification.
  - **Liskov Substitution Principle (LSP)**: Discuss the inheritance relationships, especially for **User** subclasses.
  - **Interface Segregation Principle (ISP)**: Explain the small, role-specific interfaces used (e.g., **PaymentGateway**).
  - **Dependency Inversion Principle (DIP)**: Explain how high-level modules depend on abstractions rather than specific implementations.

#### **11. Conclusion**
- **Summary of the Design Approach**:
  - Summarize how each of the steps led to a well-designed system that is easy to maintain, scale, and extend.
- **Benefits of SOLID Implementation**:
  - Explain the benefits of adhering to SOLID principles, such as reduced technical debt, easy feature additions, and improved code readability.
- **Future Work and Extensions**:
  - Describe how the design can accommodate future extensions, such as new user roles, notification channels, and integration with third-party services.

#### **12. Appendix**
- **Glossary**: Include any technical terms or abbreviations used in the document.
- **References**: Mention any resources or standards followed during the design process (e.g., software engineering books, standards, or reference materials).

### **Guidelines for Compiling the PDF Document**
1. **Use Consistent Formatting**:
   - Use a consistent font (e.g., Arial or Times New Roman).
   - Use **headings** and **subheadings** to organize sections clearly.
   - Make use of **numbered lists**, **bullet points**, and **bold** text to improve readability.
2. **Diagrams and Visuals**:
   - Ensure that all diagrams (Use Case, Class, Interaction, Package, etc.) are clear, labeled, and well-placed.
   - You can use tools like **Lucidchart**, **Draw.io**, **Microsoft Visio**, or **Figma** to create professional diagrams.
3. **Page Numbering and Headers/Footers**:
   - Include **page numbers** on each page.
   - Consider adding a **header** or **footer** with the document title or your name.
4. **Professional Layout**:
   - Add appropriate **spacing** between sections.
   - **Align** text and diagrams for a professional appearance.
   - Ensure that diagrams are not split across pages.
5. **Export to PDF**:
   - Once all content is compiled in a word processor (such as **Microsoft Word** or **Google Docs**), export the document as a **PDF**.
   - Ensure that hyperlinks (if any) are correctly embedded.

### **Tools for Compiling the Document**
- **Microsoft Word** or **Google Docs** for writing content and inserting images.
- **Lucidchart**, **Draw.io**, or **Microsoft Visio** for diagrams.
- **Figma** or **Balsamiq** for UI Mock-Ups.
- Export the final document as a PDF using the built-in export function in your word processor.

### **Deliverable: Single PDF**
has to be one massive pdf
