# Property File Encryption

In order to encrypt the data in properties file, Mule Credential Vault is used. This feature is available in EE version.

## Requirement
   1. Mule EE Version
   2. Mule Enterprise Security Module (Credential Vault)
   3. Global Secure Property Placeholder element.
   4. A key to unlock the vault.

## Installation Details
Ignore this step if Mule Enterprise Security Module is already available in Anypoint Studio.

   1. Under the Help menu, select Install New Software
   
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/MileStone2/Install.PNG)
   2. Mule opens the Install wizard. Click the Add  button next to the Work with field.
   
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/MileStone2/Install1.PNG)
   3. In the Add Repository panel, enter a Name for the repository, such as Anypoint Enterprise Security, and in the Location field,   paste the following link:
      http://security-update-site-1.4.s3.amazonaws.com
      then click OK. Then install all the below modules
      
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/MileStone2/Install3.PNG)

## Configuration Details
   
   1. In Anypoint Studio, right click the src/main/resources folder, then select New > File.
      In the New File wizard, enter a Filename, including the .properties extension. For example, secure-dev.properties.

   2. In the Package Explorer, right-click the .properties file, then select Open With > Mule Properties Editor.
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/Encrypt/Capture1.PNG)

   3. Click the green (plus) icon in the Studio toolbar (see image below) to open the Add a new property dialog.
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/Encrypt/Capture2.PNG)

   4. Add the key-value pair (property) you wish to record in the properties file. Click Finish. Studio saves the new, 
      blank file in your project and opens a new window in a Properties File Editor window. If you want to save the property
      as an unencrypted key-value pair, simply click OK to add the new property to the properties file. Essentially, this produces 
      an unencrypted properties file.However, if you wish to encrypt the properties file (i.e. create a Credentials Vault), click the   
      Encrypt button.
      
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/Encrypt/Capture3.PNG)

   5. Studio opens a Setup encryption information dialog, in which you:
      Select the type of algorithm you wish to use to encrypt the value.
      Enter the key that Mule requires when asked to decrypt the value .
      Click OK to complete the encryption.
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/Encrypt/Capture4.PNG)
     
   6. In Studio, create a new global Secure Property Placeholder element. 
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/Encrypt/Capture5.PNG)
     
   7. Configure the field values of the global element according to the table below.       
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/Encrypt/Capture6.PNG)
      
      In CloudHub, the Operations Administrator can enter the runtime.key which can also be made secured by the key/value pair in mule-  app.properties  ``` secure.properties=runtime.key ```
      
      ![ScreenShot](https://raw.githubusercontent.com/indiramallick1988/Demo2/master/Encrypt/Capture7.PNG)
      
