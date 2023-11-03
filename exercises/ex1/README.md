# Predict the plane type of an aircraft

In this exercise, we are going to predict the plane type of an aircraft using SAP BTP based ML service Data Attribute Recommendation. We will use the Intelligent Scenario Lifecycle Management (ISLM) framework to create and operate the ML use case. 

Data Attribute Recommendation uses machine learning to predict and classify data records.<br>
With Data Attribute Recommendation you can
  -	Automate and speed up data management processes
  -	Reduce errors and manual efforts in data maintenance
  -	Increase data consistency and accuracy

This exercise includes the following steps: 
1. Create and publish Intelligent Scenario.
2. Set up the connection for Intelligent Scenario to connect to BTP based ML service.
3. Use Intelligent Scenario Management app to train, view model quality, deploy and activate the model.
4. View the inference result returned by the model in an ABAP report.

## 1. Create and publish Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app. In this step, you’ll create a new intelligent scenario to predict the plane type using SAP BTP based ML service Data Attribute Recommendation. 

1. Create a Prediction Class which defines the behavior of the scenario.<br>

   Prediction class has methods to specify Inference type and ML Template for Data Attribute Recommendation. 
   For this use case, we will use generic template which make use of Classification algorithm.<br>

   
   Open **SAP Logon** and logon to system **HE4 400** <br>
   Open transaction **/nse24** and search for the ABAP class mentioned in User Details for your user group. Ctrl+Click [here](/exercises/ex5#for-attendees-001-to-008) to get the prediction class to be copied.
   <br>![](/exercises/ex1/images/1.png)
1. Click on **Copy** 
   <br>![](/exercises/ex1/images/2.png)
2. Provide the unique name in the Copy to field.<br>  
   Enter a unique name starting with ZCL, such as **ZCL_PLANTYPE_###**, where ### is your attendee id. 
   <br>Click on tick icon.
   <br>![](/exercises/ex1/images/3.png)
3. Click on **Local Object** 
   <br>![](/exercises/ex1/images/4.png)
4. Class is created in Inactive status. Click on **Display**
   <br>![](/exercises/ex1/images/5.png)
5. Click on **Activate** icon
   <br>![](/exercises/ex1/images/6.png)
6. Click on tick icon
   <br>![](/exercises/ex1/images/7.png)
7. Ctrl+Click [here](https://flp1.tdc.sap.com:44302/sap/bc/ui2/flp#Shell-home) to open Fiori Launchpad in a new tab.<br>
   Enter the user details as provided in Attendee Details. Ctrl+Click [Attendee Details](../ex5/).
   <br>
   Click on **My Home** section and choose the **Intelligent Scenario** app.
   <br>![](/exercises/ex1/images/8.png)
9. Click the **Create** button and choose->**Side-by Side**.
   This approach is commonly known as '**side-by-side**,' where the ML provider and the business application operate within separate stacks.
   <br>![](/exercises/ex1/images/9.png)
11. Provide the required information in the screen:
	1. **Intelligent Scenario Name**: Enter a unique name starting with Z, such as `Z_AI267_PLANTYPE_###` where **###** is your attendee id.
	2. **Intelligent Scenario Description**: Enter a description for the Intelligent Scenario.
	3. **Intelligent Scenario Type** as **Data Attribute Recommendation**  
   <br>![](/exercises/ex1/images/10.png)
12. Select **Prediction Class** from value help 
    <br>![](/exercises/ex1/images/11.png)
13. Click on **OK** in the information box
    <br>![](/exercises/ex1/images/12.png)
14. Select the prediction class created by you in the previous section
    <br>![](/exercises/ex1/images/13.png)
15. Scenario is now ready to be published. Click on **Publish** button. You will receive a message that Intelligent Scenario is 
    published.
    <br>![](/exercises/ex1/images/14.png)
16. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** and **Status = Published**. 
    <br>![](/exercises/ex1/images/15.png)

### Well done, you just created your first Side-by-side Intelligent Scenario.
<br>

## 2. Set up the connection for Intelligent Scenario to connect to BTP based ML service

Once the Intelligent Scenario is published, we need to maintain the connection for an intelligent scenario in SAP S/4 HANA with the Data Attribute Recommendation service in BTP. Speaker has provisioned the ML Service in BTP and  **service key** details are provided in step 7 to setup the connection. 

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
7. Enter the Service Key details. Ctrl+Click [here](../ex5/) to get Service Key details.
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

## 3. Use Intelligent Scenario Management app to train, view model quality, deploy and activate the model
Once the Intelligent Scenario is published, the Intelligent Scenario Management app helps you to train, monitor the model quality, deploy, and activate the model for productive usage.
In this section, you will use the Intelligent Scenario Management app to perform ML operations. 

1. Ctrl+Click [here](https://flp1.tdc.sap.com:44302/sap/bc/ui2/flp#Shell-home) to open Fiori Launchpad in a new tab.<br>
   Enter the user details as provided in Attendee Details. Ctrl+Click [Attendee Details](../ex5/).
   <br>
   Click on **My Home** section and choose the **Intelligent Scenario Management** app.
   <br>![](/exercises/ex1/images/27.png)
3. Search the **Plane type** scenario created by you and navigate to the details page by clicking the **>** icon. 
    <br>![](/exercises/ex1/images/28.png)
4. Select the Version **3.0** and click on the **Train** button to trigger the training.
   <br>![](/exercises/ex1/images/29.png)
5. Train dialog opens.
   The values for Parameters and Artifacts will be defaulted and do not change it.
   <br>![](/exercises/ex1/images/30.png)
6. Click on **Train** button
   <br>![](/exercises/ex1/images/31.png)
7. New Training will be created in **Scheduled** status.
   <br>![](/exercises/ex1/images/32.png)
8. Monitor the status of Training and check the status changes to **Training**
   <br>![](/exercises/ex1/images/33.png)
9. Monitor the status of Training and check the status changes to **Completed**. Note that training can take approximately 
   **5 minutes** to complete.
   <br>![](/exercises/ex1/images/34.png)
10. Click on **>** icon to view Training Report.
   <br>![](/exercises/ex1/images/35.png)
11. View the information in header section. 
    Click on **Debrief** tab.
    <br>![](/exercises/ex1/images/36.png)
12. View target metrics and feature contribution scores in **Debrief**.
    
    **Feature contribution score:** Estimate of how much the model depends on each feature. The higher the contribution 
     score, the more important the feature is.

     **Accuracy, F1Score, Precision and Recall** are classificaiton metrics. The higher the better.
    <br>![](/exercises/ex1/images/37.png)
    
13. Click on **Deploy** Button
    <br>![](/exercises/ex1/images/38.png)
14. Click on **Deploy and Monitor** Button
    <br>![](/exercises/ex1/images/39.png)
15. New Deployment will be created in **Deployment Pending** status.
    <br>![](/exercises/ex1/images/40.png)
16. Monitor the status of Deployment and check the status changes to **Deployed**. Note that Deployments can take 
    approximately **10 minutes** to be Deployed.
    <br>![](/exercises/ex1/images/41.png)
17. Activate the deployment to run inference. Select the Deployment and click on **Activate** button and choose **For All** 
    option.
    <br>![](/exercises/ex1/images/42.png)
18. In the dialog Activate for All Users, choose **Activate For All**.
    <br>![](/exercises/ex1/images/43.png)
19. Monitor that the Deployment has **Active for all** Indicator.
    <br>![](/exercises/ex1/images/44.png)

### Well done, you just Used Intelligent Scenario Management app to train, view model quality, deploy and activate the model
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

      Inference Request contains the features and its value which is input for the trained model.
      
      Your trained model is now ready to predict the target **PLANETYPE**.

      **topN**-parameter which defines how many options will be predicted.
      
      To predict this target, inputs to model has to be provided.

      Inputs would be **CARRID, CONNID, FLDATE, PRICE, SEATSMAX, SEATSOCC, SEATSMAXB, SEATSMAXF, SEATSOCCB, 
      SEATSOCCF, PAYMENTSUM, CURRENCY**.
      # Inference Request in JSON
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
5. Paste the copied text in the **text editor**. Click on **tick** icon.
   <br>![](/exercises/ex1/images/54.png)
 
6. View the response from the trained model.

   In the response, you find the values that the model predicted. This includes the value that is predicted and the 
   probability. The probability describes how certain the model is about its prediction. **If the probability is close to 1, 
   the model is very certain**.
   
   Model predicts the PLANETYPE with two possible values(as defined in Inference request **"topN": 2** )
	| Predicted Value | Probability    | 
	| :---:   | :---: | 
	| 747-400 | 0.9646   |
	| 767-200 | 0.010   | 

   
   <br>![](/exercises/ex1/images/55.png)

### Well done, you just Viewed the inference result returned by the model in an ABAP report.
<br>

## Summary
🎉 Congratulations! 🎉 <br>
You have successfully completed the Exercise 2. <br>
Now Continue to 
- [Additional Exercise](../ex3/README.md) 
         <br>OR <br>
- [Summary](../ex2/README.md)  

