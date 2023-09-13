# Unity Integration with Agora SDK 4 for 3D Spaces

This tutorial will guide you through integrating the Agora SDK into your Unity project to create a 3D space that supports real-time communication. This guide assumes you are using Unity version 2021.3.5f1 and Agora Video SDK for Unity version 4.2.2. It is very important to highlight that this implementation is designed for asymmetric collaboration. More specifically, PC and VR. So only the PC user's camera is transmitted. If you are looking for a swap of both webcams in a 3D environment then check out my repository which implements this, just change the canvas render mode from overlay to World Space in order to place both views in the scene :)
GitHub Repository: [Unity Agora SDK 4 with UI 2D Repository](https://github.com/marcor0311/unity-agora-sdk-4-with-ui-for-2d-spaces)

## Prerequisites

Before getting started, make sure you have the following:

- Unity 2021.3.5f1 installed.
- Agora Video SDK for Unity 4.2.2.
- Agora Account

Implementation is the same for both projects.
## Project Setup (create two projects with the same instructions, one for PC and one for VR)

### 1. Create a Unity Project:

- Open Unity Hub, select "Projects," and click "New Project."
- Choose the 3D template and click "Create Project."
- Open your newly created project in Unity.

### 2. Integrate Video SDK:

- Add to your assets the latest Agora Video SDK for Unity from the [Unity Asset Store](https://assetstore.unity.com/packages/tools/video/agora-video-sdk-for-unity-134502).
- In Unity, go to "Window" > "Package Manager" > "My Assets."
- Find the Agora Video SDK, click "Download," and then "Import."

### 1. Create the canvas:

- Right-click "Sample Scene" in the Unity hierarchy.
- Choose "UI" > "Canvas" to create where the video will be placed. Canvas should be Width: 1280, Height 720.
- In the Canvas Inspector, set "Render Mode" to "World Space" and place the canvas somewhere in the scene

### 2. Add Local and Remote Video Views:
For PC project:
- Create a Raw Image for the local video by right-clicking the "Canvas," choosing "UI," and selecting "Raw Image."
- Rename it to "LocalView" and size should be Width: 1280, Height 720.
- Create another Raw Image for the remote video named "RemoteView" and position it outside the scene because in the PC project it is not needed (this is just for the script to work)

For VR project:
- Create a Raw Image for the local video by right-clicking the "Canvas," choosing "UI," and selecting "Raw Image."
- Rename it to "RemoteView" and size should be Width: 1280, Height 720.
- Create another Raw Image for the local video named "LocalView" and position it outside the scene because in the VR project it is not needed (this is just for the script to work)

Canvas should look something like this in both projects
![PhotonVR-SampleScene-Android-Unity-2021 3 5f1-Personal-_DX11_-2023-09-12-23-29-22](https://github.com/marcor0311/unity-agora-sdk-4-for-3d-spaces/assets/110083517/271a40aa-3c59-407c-8757-d945ed765ecf)
(The plane is optional, I will be using it only for the demonstration, this means it is not required)

### 3. Script

The script is in this repository in "Code" > AgoraUnityNoUI.cs 

Simply add it to the canvas as a Component.
It is important that using your Agora Account you create an Agora project and complete them with the values generated in the Agora console.
```
// Fill in your app ID.
private string _appID = "";
// Fill in your channel name.
private string _channelName = "";
// Fill in the temporary token you obtained from Agora Console.
private string _token = "";
```
# Video of the final result
![Photon-PC-SampleScene-Windows_-Mac_-Linux-Unity-2021 3 5f1-Personal-_DX11_-2023-09-13-00-57-02](https://github.com/marcor0311/unity-agora-sdk-4-for-3d-spaces/assets/110083517/9ca17081-f01d-48f5-b66c-ad4e522f8b94)
(Now this video is shared between the two projects :) )


Return to the main repository: [Unity Essentials Repository](https://github.com/marcor0311/Unity-Essentials)https://github.com/marcor0311/Unity-Essentials)
