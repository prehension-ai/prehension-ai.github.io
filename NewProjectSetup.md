# New Project Setup
At the moment the only headset Prehension’s SDK is compatible with is Oculus/Meta. More headset support will come in the future!

The first steps for a new project will be to download and set up Meta’s SDKs to Unity and your headset talking. They have a tutorial here with detailed instructions, for the most part you can follow that directly.

Follow the instructions up to “Add a grab interaction” (Under “Step 3: Add Building Blocks To Your Scene”). Our plugin will take care of the hand interaction for you, so you can skip that! Instead, make sure you search for “Hands” and add that Building Block in your main scene to get your hands tracking.

Skip down to “Step 4: Preview Your Scene” and continue to follow the instructions. By the end you should be able to press play in the Unity Editor, and see the scene (empty for now) and your hands tracked in your headset.

### Adding the Prehension SDK

Click through Window > Package Management > Package Manager

Click the plus icon in the top left, much like you did to add Meta’s package. Choose “Add package from disk” and select the folder where you downloaded the Prehension SDK.

### Set Up Your Project

With the Prehension SDK you should have a new menu button in your menu bar. Choose Prehension > Setup Project. This will create a folder in your project’s Assets folder (’PrehensionData’) that will eventually contain 3 things:

- Project Details (project name, id, and access key)
- Prehension Config (central data overview, more on this later)
- Sample Data (collection of all the gesture samples you’ve recorded for your gesture recognition model)

`ProjectDetails.json` and `PrehensionConfig.asset` should exist as soon as you set up your project. `SampleData` will get filled in later.

Alex should have given you an api key, a project name, and a project id - if he didn’t, ask him. Once you have them, fill them in to the appropriate fields in `ProjectDetails.json`

When you run Setup Project you may also get a log message about needing to install TMP Essentials. If you do, do it [need to figure out exactly how that works]

Once you've got your project set up, you can move on to [Recording Data](./RecordingData.md)