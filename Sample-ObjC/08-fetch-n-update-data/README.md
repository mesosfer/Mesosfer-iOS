# Mesosfer Starter Project for iOS #


A Framework that gives you access to the powerful Mesosfer cloud platform from your iOS app. 
For more information about Mesosfer and its features, see [Mesosfer Website][mesosfer.com] and [Mesosfer Documentations][docs].

## Fetching Data
If you need to fetch a data with the latest data that is in the cloud, you can call the `fetchAsync` method like so:

```objective-c
// create data from existing objecId
MFData *data = [MFData dataWithObjectId:@"objectId"];
// fetching the data
[data fetchAsyncWithBlock:^(MFData * _Nullable data, NSError * _Nullable error) {
    if (error) {
        // data failed to fetch, show error message
        return;
    }
    
    // data fetched
}];
```

This will automatically update data with the latest data from cloud.

## Updating Data
After getting the data, you can update your data that stored in cloud using method `saveAsync`.

```objective-c
MFData *data; // fetched data

// set data
data[@"name"] = @"Beacon Two";
data[@"proximityUUID"] = @"CB10023F-A318-3394-4199-A8730C7C1AEC";
data[@"major"] = @2;
data[@"minor"] = @284;
data[@"isActive"] = @NO;
data[@"timestamp"] = [NSDate date];

// execute save data
[data saveAsyncWithBlock:^(BOOL succeeded, NSError * _Nullable error) {
    if (succeeded) {
        // data updated, show success message
    } else {
        // failed to update data, show error message
    }
}];
```

## License
    Copyright (c) 2016, Mesosfer.
    All rights reserved.

    This source code is licensed under the BSD-style license found in the
    LICENSE file in the root directory of this source tree.

[mesosfer.com]:https://mesosfer.com
[docs]:https://docs.mesosfer.com/
[cloud]:https://cloud.mesosfer.com/
[framework]:https://github.com/mesosfer/Mesosfer-iOS/releases/latest
