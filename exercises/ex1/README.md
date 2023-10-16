# Predict the plane type of an aircraft

In this exercise, we are going to predict the plane type of an aircraft using SAP BTP based ML service Data Attribute Recommendation. We will use the Intelligent Scenario Lifecycle Management (ISLM) framework to create and operate the ML use case. 

This exercise includes the following steps: 
1. Create and publish Intelligent Scenario.
2. Set up the connection for Intelligent Scenario to connect to BTP based ML service.
3. Use Intelligent Scenario Management app to train, view model quality, deploy and activate the model.
4. View the inference result returned by the model in an ABAP report.

## 1. Create and publish Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app. In this step, you’ll create a new intelligent scenario to predict the plane type using SAP BTP based ML service Data Attribute Recommendation. 

1. Create a Prediction Class which defines the behavior of the scenario.<br>
   Open **SAP Logon** and logon to system **HE4 400** <br>
   Open transaction **/nse24** and search for the class **ZCL_PLANTYPE_HO**  
   <br>![](/exercises/ex1/images/1.png)
2. Click on **Copy** 
   <br>![](/exercises/ex1/images/2.png)
3. Provide the unique name in the Copy to field.<br>  
   Enter a unique name starting with ZCL, such as **ZCL_PLANTYPE_###** ### is your attendee id. 
   <br>Click on tick icon.
   <br>![](/exercises/ex1/images/3.png)
4. Click on **Local Object** 
   <br>![](/exercises/ex1/images/4.png)
5. Class is created in Inactive status. Click on **Display**
   <br>![](/exercises/ex1/images/5.png)
6. Click on **Activate** icon
   <br>![](/exercises/ex1/images/6.png)
7. Click on tick icon
   <br>![](/exercises/ex1/images/7.png)
8. Open the Fiori Launchpad URL
   ```
   https://34.196.182.50:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html
   ```
   Input the username and password provided by the moderator.
   Click on **My Home** section and choose the **Intelligent Scenario** app.
   <br>![](/exercises/ex1/images/8.png)
9. Click the **Create** button and choose->**Side-by Side** 
   <br>![](/exercises/ex1/images/9.png)
10. Provide the required information in the screen:
	1. **Intelligent Scenario Name**: Enter a unique name starting with Z, such as `Z_FI_PLANTYPE_###` where **###** is your attendee id.
	2. **Intelligent Scenario Description**: Enter a description for the Intelligent Scenario.
	3. **Intelligent Scenario Type** as **Data Attribute Recommendation**  
   <br>![](/exercises/ex1/images/10.png)
11. Select **Prediction Class** from value help 
    <br>![](/exercises/ex1/images/11.png)
12. Click on **OK** in the information box
    <br>![](/exercises/ex1/images/12.png)
13. Select the prediction class created by you in the previous section
    <br>![](/exercises/ex1/images/13.png)
14. Scenario is now ready to be published. Click on **Publish** button. You will receive a message that Intelligent Scenario is 
    published.
    <br>![](/exercises/ex1/images/14.png)
15. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** and **Status = Published**. 
    <br>![](/exercises/ex1/images/15.png)

### Well done, you just created your first Intelligent Scenario.
<br>

## 2. Set up the connection for Intelligent Scenario to connect to BTP based ML service

Once the Intelligent Scenario is published, we need to maintain the connection for an intelligent scenario in SAP S/4 HANA with the Data Attribute Recommendation service in BTP. Moderator has provisioned the ML Service in BTP and will share the service key to setup the connection. 

1. Open **SAP Logon** and logon to **HE4 400**<br>
   Open transaction **/nSPRO**<br>
   Click **SAP Reference IMG** 
   <br>![](/exercises/ex1/images/16.png)
2. Click on **Yes** to proceed
   <br>![](/exercises/ex1/images/17.png)
3. Navigate to **ABAP Platform >Application Server >Basis Services >Intelligent Scenario Lifecycle Management> Service Connections for 
   Machine Learning Infrastructure > Maintain Connection for an Intelligent Scenario**.
   <br>![](/exercises/ex1/images/18.png)
4. Click on **Execute**
    <br>![](/exercises/ex1/images/19.png)
5. The ISLM Connection Mapping window opens. Click the **Create Connection** icon. 
   <br>![](/exercises/ex1/images/20.png)
6. Input the Intelligent Scenario Name and click on **Next**
   <br>![](/exercises/ex1/images/21.png)
7. Enter the **service key** from remote machine learning provider shared by the moderator.
   <br>![](/exercises/ex1/images/22.png)
8. Click **Next**.
   <br>![](/exercises/ex1/images/23.png)
9. Perform **Connection Check** to know the health of ML provider.
    <br>![](/exercises/ex1/images/24.png)
10. Check the Connection Status changes to **Ready**. Click **Save**.
    <br>![](/exercises/ex1/images/25.png)
11. New entry will be added to the table.
    <br>![](/exercises/ex1/images/26.png)

### Well done, you just Set up the connection for Intelligent Scenario to connect to BTP based ML service.
<br>


## 4. View the inference result returned by the model in an ABAP report
  In this step, you will use the ABAP GUI to view the inference result from the trained model.

   1. Logon to system **HE4** open transaction **/nSE38**
      <br>![](/exercises/ex1/images/50.png)
   2. Input Report Name as
      ```
      R_ISLM_TEST_OPERATION_API
      ```
       and Click on **Execute** Button
      <br>![](/exercises/ex1/images/51.png)
   3. In the API Definition, choose option **TRIGGER_ONLINE_INFERENCE** from drop down.
      <br>![](/exercises/ex1/images/52.png)
   4. Enter the prediction class associated with your Intelligent Scenario.
      Click on **Execute**.
      <br>![](/exercises/ex1/images/53.png)
      <br>
      Copy the below text which contains the Inference Request in JSON format.
      # JSON
```json
{
    "topN": 2,
    "objects": [
        {
            "objectId": "optional-identifier-5",
            "features": [
                {
                    "name": "CARRID",
                    "value": "AA"
                },
                {
                    "name": "CONNID",
                    "value": "17"
                },
                {
                    "name": "FLDATE",
                    "value": ""
                },
                {
                    "name": "PRICE",
                    "value": "422.94"
                },
                {
                    "name": "SEATSMAX",
                    "value": "385"
                },
                {
                    "name": "SEATSOCC",
                    "value": "374"
                },
                {
                    "name": "SEATSMAXB",
                    "value": "31"
                },
                {
                    "name": "SEATSMAXF",
                    "value": "21"
                },
                {
                    "name": "SEATSOCCB",
                    "value": "29"
                },
                {
                    "name": "SEATSOCCF",
                    "value": "21"
                },
                {
                    "name": "PAYMENTSUM",
                    "value": ""
                },
                {
                    "name": "CURRENCY",
                    "value": ""
                }
            ]
        }
    ]
}
```
5. Paste the copied text in the **text editor**.
   Inference Request contains the features and its value which is input for the trained model.Click on **tick** icon.
   <br>![](/exercises/ex1/images/54.png)
 
6. View the response from the trained model.
   Output contains the value of the target along with the probability score. 
   <br>![](/exercises/ex1/images/55.png)

### Well done, you just Viewed the inference result returned by the model in an ABAP report.
<br>

## Summary
Congratulations! You have successfully completed the Exercise 2.
Now Continue to - [Summary](../ex2/README.md)

