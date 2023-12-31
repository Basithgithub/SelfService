## **<center>Self-Service</center>** 

> Note:
   We have three selfservice apps 
   - [`Mawarid-SelfService`](https://portal.mawarid.com.sa/System/#/SelfService/authgateway)
   - [`Sawaid-SelfService`](https://portaltest.sawaidsa.com:8443/System/#/SelfService/authgateway)
   - [`Jussur-SelfService`](https://crm-api-dev.jussuremdad.com:446/System/#/SelfService/authgateway)

## <ins>Postman Collection</ins>
   [`SelfService Api Collection Link`](Collection\SelfServiceApi.json)
   > Note:
   - This Collecetion will show as a json please download this file and import in postman to test and viewing purpose
   - For Jusur and sawaid please change the respective URL and in the body change *company* to *SWD* for sawaid and *Jehr*

## **<center>About Self-Service</center>**

 - [`Click Here`](https://portal.mawarid.com.sa/System/#/SelfService/authgateway) - SelfService Application Page
 - Selfservice app maing works with *Leave request*, *Loan request*, and *Business trip*

## **<ins>Leave Request</ins>**
- A leave request is a message in which you ask your employer or supervisor for time off work. Typically, in the message, you'd state the reason behind your request and specify the dates that you want to take off
- Leave request has *Show pending* -> *Draft* -> *Submitted* ->*Approved* -> *Reject* -> *cancel* stages
- *api/v1/entitytype/wfstageaction* This is the api for stage movement while moving data from one stage to another
- In this request data will show in each format based on the stage 
- It has export option for multiple data get and import process for multiple data import
- In this request for create it calls *1,getEmployeeDetailsByEmployeeIdOrName*
*2,api/v1/security/documenttype/showattachement*
*3,api/v1/categoryrequestertype*
- A Star in the fields while creating leave requests are mandatory fields which are required 
- On *Approved* stage we calls api *https://almawarid.operations.dynamics.com/api/services/MWMawaridServiceGroup/MWMawaridService/submitLeaveRequestToWF* with body
*"Body":"{"_leaveRequestId":"@@Data.ERPRequestId""_submitterUserId":"admin","_status":"Approved","_legalEntity":"MWD"}"*
> Note: On submit leave request *_submitterUserId* is assigned as *admin*
- While creating leave request we call api using event *api/v1/recruitment/CreateSelfServiceRequestERP*
> Note: This api is used to create data on erp 

## **<ins>Loan Request</ins>**
 - Loan Request means a request by the Borrower, executed by a Responsible Officer of the Borrower
 - Loans may be for a specific, one-time amount, or they may be available as an open-ended line of credit up to a specified limit. Loans come in many different forms including secured, unsecured, commercial, and personal loans.
 - Loan request has *Show pending* -> *Draft* -> *Submitted* ->*Approved* -> *Reject* -> *cancel* stages
 - A Star in the fields while creating Loan requests are mandatory fields which are required 
 - *api/v1/entitytype/wfstageaction* This is the api for stage movement while moving data from one stage to another
 - In this request data will show in each format based on the stage 
 - It has export option for multiple data get and import process for multiple data import
 - In this request for create it calls *1,getEmployeeDetailsByEmployeeIdOrName*
*2,api/v1/categoryrequestertype*
*3,api/v1/erp/getReportingManagerForEmployee*
*4,api/v1/security/documenttype/showattachement*
- On *Approved* stage we calls api *https://almawarid.operations.dynamics.com/api/services/MWMawaridServiceGroup/MWMawaridService/submitLeaveRequestToWF* with body
*"Body":"{"_leaveRequestId":"@@Data.ERPRequestId""_submitterUserId":"admin","_status":"Approved","_legalEntity":"MWD"}"*
> Note: On submit leave request *_submitterUserId* is assigned as *admin*
- While creating leave request we call api using event *api/v1/recruitment/CreateSelfServiceRequestERP*
> Note: This api is used to create data on erp 

## **<ins>Business Trip</ins>**
 - A Visit made to a place for work purposes, typically one involving a journey of some distance.
"A Business trip offers a break from the daily office routine"
 - A Star in the fields while creating Business trip request are mandatory fields which are required 
 - Business trip request has *Show pending* -> *Draft* -> *Submitted* ->*Approved* -> *Reject* -> *cancel* stages
 - *api/v1/entitytype/wfstageaction* This is the api for stage movement while moving data from one stage to another
 - In this request data will show in each format based on the stage 
 - It has export option for multiple data get and import process for multiple data import
 - In this request for create it calls *1,getEmployeeDetailsByEmployeeIdOrName*
*2,api/v1/categoryrequestertype*
*3,api/v1/erp/getReportingManagerForEmployee*
*4,api/v1/security/documenttype/showattachement*
*5,/api/v1/entitytype/form*
- On *Approved* stage we calls api *https://almawarid.operations.dynamics.com/api/services/MWMawaridServiceGroup/MWMawaridService/submitLeaveRequestToWF* with body
*"Body":"{"_leaveRequestId":"@@Data.ERPRequestId""_submitterUserId":"admin","_status":"Approved","_legalEntity":"MWD"}"*
> Note: On submit leave request *_submitterUserId* is assigned as *admin*
- While creating leave request we call api using event *api/v1/recruitment/CreateSelfServiceRequestERP*
> Note: This api is used to create data on erp 

## **<ins>Leave Request Create</ins>**
- On Leave request create on loading for we set an value for employee id (User who logged in currentuser)*LocalUserInfo.EmployeeId*
- on default today date patch we use *TodayDatePipe 'DATE'*
- On rules we update the default values for the following fields *Ticket for*, *Ticket cost on*, *destination type*,*ticket class*, *depature from*, *Visa for*, *VisaCost on* fields
- While changing employee id we call api of *api/v1/erp/getReportingManagerForEmployee* with URL parameter of *_employeeid*, *_Company* and *user-id*
- While changing VacationType we triggers the field VacationCode
- On Startdate change we user the handle bar for start date as *DatePipe StartDate 'DATE'* and again we triggers the Vacation code, It automatically set the end date with use of *AddtionalDatePipe StartDate VacationDays *
- On end date change we set an enddate by handle bar *DatePipe EndDate 'DATE'* as simailar to start date
- On adition of enddate we set an value of ExpectedReturnDate by the help of the handle bar *AddtionalDatePipe EndDate '1' * and again we triggers the vacationcode 
- On VacationDays Change it triggers the start date ang it will change readonly to changeable field
- on AdultTicketsUsed, InfantTicketsUsed, VisaUsed, VisaEntitlement it triggers the vacationcode changes
- On AlternativeEmployeeId Change it triggers AlternativeEmployeeName and patches default employee id with the help of *data.employeeName*
- On vactioncode change it triggers the *api/v1/erp/InitiateLeaveRequest* Api with params of user-id(Note: If you need this api for testion and devolepment purpose download api collection in above mentioned link and import it in postman)
- On vacationDaysExtTwo Change for te field endDateExtend two we use *CurrentAdditionalDatePipe startDateExtTwo vacationDaysExtTwo* handlebar and for endDateExtTwoString we use *DatePipe endDateExtTwo 'DATE'*
- On vacationDaysExtOne Change for the field endDateExtOne we use *CurrentAdditionalDatePipe startDateExtOne vacationDaysExtOne* and endDateExtOneString *DatePipe endDateExtOne 'DATE'* handlebars
- on vacationTypeExTwo change we set an value for startDateExtTwo, startDateExtTwoString as handlebar *AddtionalDatePipe endDateExtOne '1'* and *DatePipe startDateExtTwo 'DATE'*


## **<ins>Loan Request Create</ins>**

- On Loan request create we set an employeeid as *LocalUserInfo.EmployeeId*
- While changing employee id we call api of *api/v1/erp/getReportingManagerForEmployee* with URL parameter of *_employeeid*, *_Company* and *user-id*
- On LoanProfileId Change we set an value for loantype, oyher loan type, loan Profile recid, effective date as from pipes *data.loanType*, *data.otherLoanTypeId*, *data.recId*
- On EffectiveDate Change we set an value for EffectiveDateString as *DateToStringPipe EffectiveDate 'mm-dd-yyyy'* 
- On EffectiveDate Change we all an restapi *api/v1/erp/InitiateLoanRequest*
> Note: For more info about the above mentioned api please download the postman collection attached in the document 

## **<ins>Business Trip Create</ins>**

- On Business trip create we set an employeeid as *LocalUserInfo.EmployeeId*
- On loading bussiness trip create we load api *api/v1/erp/InitiateBusinessRequest* while loading business trip create form 
> Note: For more info about the above mentioned api please download the postman collection attached in the document 
-  While changing employee id we call api of *api/v1/erp/getReportingManagerForEmployee* with URL parameter of *_employeeid*, *_Company* and *user-id*



## **<ins>Login Page</ins>**
   ![N|Solid](assets\LoginPage.png)
 - In Self-service we have two types of login [`Active-Directory`](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn283324(v=ws.11)) and [`Authgateway-Login`](https://portal.mawarid.com.sa/System/#/SelfService/authgateway)
> Note:
   - For Active-directory login we need credentials that are registed in azure, For configuration purpose we need (ClientId, Authority,  and RedirectURL)
   - For Authgateway-Login it works under the (LoginComponent and Authgateway Components, For more info and flow please check in the UI Code)
   - Login Credential for Authgateway-Login `User-Name:a.hyder` and `Password:123456`
 
## **<center>Menus In Self-Service</center>**

![N|Solid](assets\TopMenu.png)
## **<ins>Top Menu</ins>**

- In this Top menu we are able to redirect to our other apps 

## **<center>Side Menu</center>**

   - Dashboard
   - My Appoval
   - Requests
   - My Requests
   - Security
   - All Requests

## **<ins>Dashboard</ins>**

![N|Solid](assets\Dashboard.png)
- In Dashboard we have an three tiles named as *Leave request create*, *Loan request create*, and *Business trip create*, By clicking this tile you have been redirect to the create page of *Leave request create*, *Loan request create*, and *Business trip create*
- To DashBoard page [`Click here to redirect to dashboard`](https://portal.mawarid.com.sa/System/#/SelfService/NewSelfServiceDashboard)

## **<ins>My Approval</ins>**

- My approval has three sub-menus LeaveRequest, LoanRequest, and BusinessTrip
- In this sub-menu LeaveRequest, LoanRequest, and BusinessTrip we can assign an single request or using import data using excel sheets (import data) for bult datas 
- This My approval menu has approve and reject for users under our management

## **<ins>Requests</ins>**

- Requests has submenu Selfservice which has LeaveRequest, LoanRequest, and BusinessTrip(Requests->Selfservice->LeaveRequest, LoanRequest, and BusinessTrip)
- In this we have seven stages(ShowPending, Draft, Submitted, Approved, Reject/Cancel, Error and ShowAll)
- In pending stage we have the datas of the pending LeaveRequest, LoanRequest, and BusinessTrip which was created and not approved
- Next stage of pending is draft, To change stages we need to click the action button
- By clicking the action button we can change the stage of the request 


## **<ins>My Requests</ins>**

- In this Menu we can create our personal requste for Leave, Loan and business Trip Purpose

## **<ins>Security</ins>**

- In this menu we have *user-list* , we can create users for the selfservice and need to assign role for the users, This meni also has the feature for creating bulk users by export and imports datas using excel sheets

## **<ins>All Requests</ins>**

- In this menu we will have all the requstes includes(`Personal, General, and Stages based LeaveRequest, LoanRequest, and BusinessTrip Requests`) 


