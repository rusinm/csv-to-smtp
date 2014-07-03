# Sending a CSV file to gmail using SMTP


This example shows you how to use the SMTP connector to facilitate information transfer through email. It also illustrates how you can use the File connector to input a a csv file and then tranform it using the daatmapper transformer.

### Assumptions

This document describes the details of the example within the context of Anypoint™ Studio, Mule ESB’s graphical user interface (GUI). This document assumes that you are familiar with Mule ESB, [Datamapper](http://www.mulesoft.org/documentation/display/current/Datamapper+User+Guide+and+Reference) and the [Anypoint Studio interface](http://www.mulesoft.org/documentation/display/current/Anypoint+Studio+Essentials). 

### Example Use Case

In this example a CSV file containing sample sales data which is stored in the local directory is converted to the JSON format using the datamapper and is sent to an email address using the SMTP connector. The Datamapper also computes the total price for each order by multiplying the unit price with the number of units. This example has been configured for Google's gmail.

### Set Up and Run this Example

Step 1: **Open** the project in the studio interface

Step 2: **Create** a directory called 'test' on your Desktop

Step 3: Navigate to src.main.resources under src/main/app and **edit common.properties** as follows:

    path.to.dir=/users/username/desktop/test
 
    # SMPT Services configuration
    smtp.host=smtp.gmail.com
    smtp.port=587
    smtp.user=senderemailid%40gmail.com
    smtp.password=senderpassword

    # Mail details
    mail.from=senderemailid@gmail.com
    mail.to=receiveremailid@gmail.com
    mail.subject=Export from Excel
    
Step 4: **Run** the project as a Mule application

Step 5: Navigate to src.main.resources under src/main/app and **copy the 'input.csv' file** into the test folder that you just created on your Desktop. If you have configured and run this example correctly, the csv file should disappear from the the test folder almost immediately.

Step 5: Login to receiveremailid@gmail.com to **verify** if the sales data was received via email in a JSON format. You should get an email that has the following content:

    [{orderId=1, name=aaa, units=2.0, pricePerUnit=10.0, totalPrice=20.0}, {orderId=2, name=bbb, units=4.15, pricePerUnit=5.0, totalPrice=20.75}]

### Go Further

* Read more about the [SMTP Connector](http://www.mulesoft.org/documentation/display/current/SMTP+Transport+Reference)

* Read more about the [File Connector](http://www.mulesoft.org/documentation/display/current/File+Transport+Reference)

* Read more about the [Datamapper Transformer](http://www.mulesoft.org/documentation/display/current/Datamapper+User+Guide+and+Reference)
