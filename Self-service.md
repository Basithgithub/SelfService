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

 ## **<ins>Login Page</ins>**
   ![N|Solid](assets\LoginPage.png)

   In Self-service we have two types of login [`Active-Directory`](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn283324(v=ws.11)) and [`Authgateway-Login`](https://portal.mawarid.com.sa/System/#/SelfService/authgateway)
> Note:
   - For Active-directory login we need credentials that are registed in azure, For configuration purpose we need (ClientId, Authority,  and RedirectURL)
   - For Authgateway-Login it works under the (LoginComponent and Authgateway Components, For more info and flow please check in the UI Code)
   - Login Credential for Authgateway-Login `User-Name:a.hyder` and `Password:123456`
 
 ## **<center>Menus In Self-Service</center>**
 ## **<ins>Top Menu</ins>**
![N|Solid](assets\TopMenu.png)
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

## **<center>Dev Mode</center>**
-DevMode is a short form of devoleper mode which helps devolepers to change, configure activities without changes in code if we need to enable the DevMode *Press f12* -> *go-to application* -> *LocalStorage* -> Add *DevMode* as *True* as shown in the below menu

![N|Solid](assets\DevMode.png)

-In this devmode we able to change the configurations of form, menus, fields, assigning users and roles for the users

![N|Solid](assets\menu2.png)

## **<center>SelfService Credentials</center>**

### **<ins>Server Credentials</ins>** 

- Ip Address: 172.16.1.109,
- User Name : MW\p.dev,
- Password : Dev@4569

### **<ins>Deployment Path</ins>**

- Deployment Path for Self-Service : C:\App\System

### **<ins>Database Credentials</ins>**

- Ip Address: 172.16.1.109,
- username : sa
- Password : 3mpP0rt@321



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

 ## **<ins>Login Page</ins>**
   ![N|Solid](assets\LoginPage.png)

   In Self-service we have two types of login [`Active-Directory`](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn283324(v=ws.11)) and [`Authgateway-Login`](https://portal.mawarid.com.sa/System/#/SelfService/authgateway)
> Note:
   - For Active-directory login we need credentials that are registed in azure, For configuration purpose we need (ClientId, Authority,  and RedirectURL)
   - For Authgateway-Login it works under the (LoginComponent and Authgateway Components, For more info and flow please check in the UI Code)
   - Login Credential for Authgateway-Login `User-Name:a.hyder` and `Password:123456`
 
 ## **<center>Menus In Self-Service</center>**
 ## **<ins>Top Menu</ins>**
![N|Solid](assets\TopMenu.png)
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

## **<center>Dev Mode</center>**
-DevMode is a short form of devoleper mode which helps devolepers to change, configure activities without changes in code if we need to enable the DevMode *Press f12* -> *go-to application* -> *LocalStorage* -> Add *DevMode* as *True* as shown in the below menu

![N|Solid](assets\DevMode.png)

-In this devmode we able to change the configurations of form, menus, fields, assigning users and roles for the users

![N|Solid](assets\menu2.png)

## **<center>SelfService Credentials</center>**

### **<ins>Server Credentials</ins>** 

- Ip Address: 172.16.1.109,
- User Name : MW\p.dev,
- Password : Dev@4569

### **<ins>Deployment Path</ins>**

- Deployment Path for Self-Service : C:\App\System

### **<ins>Database Credentials</ins>**

- Ip Address: 172.16.1.109,
- username : sa
- Password : 3mpP0rt@321



