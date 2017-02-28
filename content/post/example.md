---
date: 2017-02-28T09:22:37-06:00
draft: false
title: example

description: This is an example blog post
author:
  name: Michael Smith Jr
  link: http://michaeldsmithjr.com
  github: msmith95
  bio: Some dude.
  image: ME.jpg
tags: [ "Development"]
excerpt: "This is an example excerpt"
authors: ["Michael"]
---

# Integrating Google Firebase and iOS without Cocoa Pods
If you’ve ever wanted to add any of Google’s Firebase services into your iOS application, you’ve probably realized that it requires Cocoa Pods. For many of the developers I know, myself included, we prefer not to involve Cocoa Pods if at all possible for many reasons. The biggest reason is that it can be difficult to decouple Cocoa Pods from the project should it be decided to use  a different set of libraries that don’t use Cocoa Pods

If you’re comfortable using Cocoa Pods for you’re project then you can skip the rest of this post and just use Google documentation found [here](https://firebase.google.com/docs/ios/setup).

## First steps
The first step is to download Google’s Firebase frameworks for iOS which can be found [here](https://firebase.google.com/docs/ios/setup#frameworks). After downloading the zip, unzip it somewhere you feel comfortable. After you’ve done that, go ahead and open your project in Xcode if you haven’t already.

Within you’re unzipped Firebase folder, open the Analytics folder and drag all of the frameworks into the root of your Xcode project. They should automatically appear in the **Linked Libraries and Frameworks** for your project, but if they don’t add them now. You will also need to add the sqlite3.tbd framework by clicking the **+** button under the **Linked Libraries and Frameworks** section and search for “sqlite3.tbd”. Lastly, drag the Firebase.h file into your project folder.

Lastly, open your project file and click **Build Settings**. In the search bar type **linker**. Look for the line that’s titled **Other linker flags** and double-click on it. Double-click on the first box and enter the following: 
```
$(OTHER_LDFLAGS) -lc++ -ObjC
```

At this point, we have added the base requirements to our project in order make it compile with Google Firebase.

## Additional Firebase Components
The following table lists the frameworks and libraries required by each component. To add each component to your project, simply drag all of the frameworks from the folder named after the component in the unzipped Firebase SDK.

| Component  | Frameworks | Libraries |
| ------------- | ------------- |-------------|
| Admob | AudioToolbox, AVFoundation,  CoreMedia,  MediaPlayer,  MessagesUI,  CoreMotion, GLKit, CoreTelephony, MobileCoreServices  | None |
| App Indexing | None | None |
| Auth | None | None |
| Firebase Crash | None | None |
| Database | None | libicucore.tbd | 
| Dynamic Links | WebKit | None | 
| Invites | WebKit, AddressBook, AssetsLibrary, SafariServices, MessagesUI | None |
| Messaging | None | None |
| RemoteConfig | None | None |
| Storage | MobileCoreServices | None |
