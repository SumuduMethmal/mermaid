---
title: ZTE
---
erDiagram
  
    Employee {<u>EmployeeID</u>; Name; Designation; JoinDate; TerminationDate; Salary; Email; MobileNumber; Address}
    CityOffice {<u>CityOfficeID</u>; Name; Address; PostalCode; PhoneNumber}
    Vehicle {<u>VehicleID</u>; LicensePlateNumber; PassengerCapacity; Make; Model; YearOfManufacture; CountryOfRegistration; RouteID} --> Route {<u>RouteID</u>; ExpectedDuration}
    Stop {<u>StopID</u>; GeographicalCoordinates} -->| Route {<u>RouteID</u>; ExpectedDuration}
    MaintenanceTask {<u>MaintenanceTaskID</u>; StartDate; EndDate; Description; RequestReferenceNumber}
    ODMR {<u>RequestReferenceNumber</u>; RequestDate; HandOverDate; ReturnDate; Details; EmployeeID} --> Employee {<u>EmployeeID</u>; Name; Designation; JoinDate; TerminationDate; Salary; Email; MobileNumber; Address}
    VehicleOperator <-> Employee {<u>EmployeeID</u>; Name; Designation; JoinDate; TerminationDate; Salary; Email; MobileNumber; Address}
    MechanicalEngineer <-> Employee {<u>EmployeeID</u>; Name; Designation; JoinDate; TerminationDate; Salary; Email; MobileNumber; Address}
    Employee <-> CityOffice {<u>EmployeeID</u>; Name; Designation; JoinDate; TerminationDate; Salary; Email; MobileNumber; Address} : WorksAt { StartDate; EndDate }
    VehicleOperator --> Vehicle {<u>VehicleID</u>; LicensePlateNumber; PassengerCapacity; Make; Model; YearOfManufacture; CountryOfRegistration; RouteID} : Drives
    MechanicalEngineer <-> Vehicle {<u>VehicleID</u>; LicensePlateNumber; PassengerCapacity; Make; Model; YearOfManufacture; CountryOfRegistration; RouteID} : Maintains
    MechanicalEngineer <-> MaintenanceTask {<u>MaintenanceTaskID</u>; StartDate; EndDate; Description; RequestReferenceNumber} : Performs
    Employee --> ODMR {<u>RequestReferenceNumber</u>; RequestDate; HandOverDate; ReturnDate; Details; EmployeeID} : Requests
    GovernmentAuthority <-> Vehicle {<u>VehicleID</u>; LicensePlateNumber; PassengerCapacity; Make; Model; YearOfManufacture; CountryOfRegistration; RouteID} : Inspects { InspectionDate; InspectionType; Feedback }
    MechanicalEngineer <-> GovernmentAuthority : ParticipatesIn


