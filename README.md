[ ![Download](https://api.bintray.com/packages/humanteq/hqm-sdk/hqm-core-legacy/images/download.svg?version=2.0.0-alpha05-fix2) ](https://bintray.com/humanteq/hqm-sdk/hqm-core-legacy/2.0.0-alpha05-fix2/link)

### HQMonitor Unity Sample App.

Unity package: [hqm_2.0.0-alpha05-fix2.unitypackage](https://github.com/HumanteQ/HQMonitorLegacyExample/raw/master/hqm_2.0.0-alpha05-fix2.unitypackage)

###### Integration instructions:

1. Install [Play Services Resolver](https://github.com/googlesamples/unity-jar-resolver/)
2. Download and import [hqm_2.0.0-alpha05-fix2.unitypackage](https://github.com/HumanteQ/HQMonitorLegacyExample/raw/master/hqm_2.0.0-alpha05-fix2.unitypackage)

   `(Assets -> Import package -> Custom package -> hqm_2.0.0-alpha05-fix2.unitypackage )`
3. Force resolve dependencies:

   `(Assets -> Play Services Resolver -> Android Resolver -> Force Resolve)`
4. Initialize SDK:
```csharp
            ...
            
            // Init SDK
            HQSdk.init(
                "your_api_key",     // your api key
                true);              // is debug enabled
               
            // Start SDK
            HQSdk.start();
               
            // Send event as text ...
            HQSdk.logEvent("test_event", "test");
            
            // ... or as a map.
            Dictionary<string, string> map = new Dictionary<string, string>();
            map["test1"] = "test_value1";
            map["test2"] = "test_value2";

            HQSdk.logEvent("test_event", map);
            
            // Request predicted user group id list ...
            var groupIdList = HQSdk.getGroupIdList();
            
            // ... or user group name list
            var getGroupNameList = HQSdk.getGroupNameList();
            
            ...
```

Startup script example: [HqmUnity.cs](https://github.com/HumanteQ/HQMonitorLegacyExample/blob/master/Assets/HqmPlugin/HqmUnity.cs)
