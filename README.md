# Vuforia_SDK_Image_Target

**Prerequisites**
  1. Unity 2020.3.23f1
  2. Vuforia Engine 10.5 from [here](https://developer.vuforia.com/downloads/sdk) (Add Vuforia Engine to a Unity Project)
  3. Register with Vuforia as a developer and get your license key

**Setting up Vuforia Engine with Unity**
  1. Grab the latest vuforia upgrade package from the link above
  2. Drag and drop the downloaded package into your  and it should prompt an import window. Click Import. ![image](https://user-images.githubusercontent.com/43946298/155774491-0033301f-7342-4a88-af7b-21d3594d318e.png)
  3. Unity will ask if you want to always have the updated vuforia engine. Click Update.![image](https://user-images.githubusercontent.com/43946298/155775026-8c24889e-c1aa-4ebc-be98-7641c42864de.png)

**Setting up a Vuforia Enabled Scene**
  1. Vuforia needs its own camera setup to work. Lets first delete the Main Camera gameobject from the scene Hierarchy and add a Vuforia Camera by going to **Gameobject -> Vuforia Engine -> AR Camera.**![image](https://user-images.githubusercontent.com/43946298/155775779-5da306df-82aa-4c13-af9b-efd8ca7b7a1b.png)
  2. Once that’s done we need to configure our project with an app license key provided by vuforia. You can generate this license key by signing up with Vuforia as a developer. A guide on how to do that can be found [here](https://library.vuforia.com/articles/Solution/How-To-Register-as-a-Vuforia-Developer).
  3. Once you are registered, go to the License Manager tab at the developer portal page(developer.vuforia.com) and **Get Basic**. Development keys are free.![image](https://user-images.githubusercontent.com/43946298/155796827-b24a1565-946e-4018-a277-85db6c649db7.png)
  4. Name your key and confirm. ![image](https://user-images.githubusercontent.com/43946298/155797257-053ebd99-6ccc-44d3-ab51-fafaa8947f05.png)
  5. Copy the key. We will then paste this key in our Vuforia Configuration which can be found under Assets/Resources/VuforiaConfiguration in the project window. Paste it under the App License Key field. ![image](https://user-images.githubusercontent.com/43946298/155797786-11806ac0-ff8d-4f34-9d53-f42d8dee0965.png)

**Creating Image Targets and Databases**
  1. Databases and targets have to be created from the Vuforia developer portal. Navigate to the Target Manager on the portal website and create a new Database. Name it and select the type as Device. ![image](https://user-images.githubusercontent.com/43946298/155799303-54c73355-0c71-4909-9ce3-65a63e245fdc.png)
  2. Once created open it select Add Target ![image](https://user-images.githubusercontent.com/43946298/155799353-352a2e94-be59-44af-9fa6-872c699650fe.png)
  3. Set the type to Single Image and browse and upload your image. You can also use the demo Image I used from here. Set the width to 0.3 which defines the size of the selected image in Unity Scene Units. Finally, click Add ![image](https://user-images.githubusercontent.com/43946298/155799436-17f57534-0926-419e-858a-7c8e18629d41.png)
  4. Vuforia will then analyze the image and show the detected features in the selected image. More the features, the better the identification and tracking ![image](https://user-images.githubusercontent.com/43946298/155799615-36d9635c-4ed5-4843-9ff9-1e0aec50cd89.png)
  5. Back on the selected database page, select the Database and click on Download Database ![image](https://user-images.githubusercontent.com/43946298/155799673-edbcf73a-48b8-4108-89cc-70af703436fc.png)
  6. It will ask for the development platform. Select Unity Editor and click on Download. ![image](https://user-images.githubusercontent.com/43946298/155799731-dbe8c981-0b4b-4191-876b-438c6cbb57be.png)

**Importing Databases into the Project**
  1. Once you have downloaded the selected Database, drag and drop into the Unity Asset Store and it should open an import window and click on Import.

**Configuring Scene with Image Targets**
  1. To create a new Image Target go to Gameobject -> Vuforia Engine -> Image.
  2. This will create a new gameobject in the Hierarchy. Select it and it should have an Image Target Behaviour component attached to it. Set its type to From Database, Database to demodatabase (the one we just created on the developer portal), and Image target to the Image name we uploaded, generated and imported into our project.
  3. Now to spawn an object or anything else on the detected Image, we basically create the object and make it a child of the Image Target gameobject. Vuforia will disable this on start and enable/track this once the parent Image target has been identified.

**Building and Running the Application**
  1. Before we build out and run the application we need to configure our player settings. Go to File -> Build Settings -> Add Open Scenes, this should add your main scene to the build.
  2. 


         
       
