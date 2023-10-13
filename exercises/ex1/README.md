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

## Exercise 1.2 Sub Exercise 2 Description

After completing these steps you will have...

1.	Enter this code.
```abap
DATA(lt_params) = request->get_form_fields(  ).
READ TABLE lt_params REFERENCE INTO DATA(lr_params) WITH KEY name = 'cmd'.
  IF sy-subrc <> 0.
    response->set_status( i_code = 400
                     i_reason = 'Bad request').
    RETURN.
  ENDIF.

```

2.	Click here.
<br>![](/exercises/ex1/images/01_02_0010.png)


## Summary

You've now ...

Continue to - [Exercise 2 - Exercise 2 Description](../ex2/README.md)

