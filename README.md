# ApplitoolsTestResultsHandler - DotNet
### v2.0.1

The Applitools Test Results Handler extends the capabilities of TestResults with additional API calls.
With these additional API calls you will be able to retrive additional details at the end of the test.

Note: The Test Results Handler requires your account View Key - which can be found in the admin panel. Contact Applitools support at support@applitools.com if you need further assistance retrieving it.

## The images that can be downloaded are:

- The test baseline image - Unless specified, the images will be downloaded to the working directory.

- The actual images - Unless specified, the images will be downloaded to the working directory.

- The images with the differences highlighted - Unless specified, the images will be downloaded to the working directory.

- Get the status of each step [Missing, Unresolved, Passed, New]

### How to use the tool:

##### To initialize the Handler:
```C#
TestResults results = eyes.Close(false);
var testResultHandler = new ApplitoolsTestResultsHandler.ApplitoolsTestResultsHandler("ViewKey", results);
```

##### **downloadDiffs** -  Downloading the test images with the highlighted detected differences to a given directory. In case of New, Missing or passed step no image will be downloaded.
```C#
testResultHandler.downloadDiffs(Path_to_directory);
```

##### **downloadBaselineImages** -  Downloading the test baseline images to a given directory
```C#
testResultHandler.downloadBaselineImages(Path_to_directory);
```

##### **downloadCurrentImages** - Downloading the test current image to a given directory.
```C#
testResultHandler.downloadCurrentImages(Path_to_directory);
```

##### **downloadImages** - Downloading the test baseline image and current image to a given directory.
```C#
testResultHandler.downloadImages(Path_to_directory);
```

##### **setPathPrefix** -  Setting this path prefix will determine the structure of the repository for the download images
```C#
testResultHandler.setPathPrefixStructure("TestName/AppName/Viewport/hostingOS/hostingApp");
```

##### In addition to downloading the images of the test, TestResultHandler also gives access through code to the visually comparison result per step. It returns an array of elements called RESULT_STATUS which can be one of the following four options: PASS, UNRESOLVED, NEW or MISSING
```C#
RESULT_STATUS[] = testResultHandler.calculateStepResults();
```


# Further regarding:

Getting Diff Images Manually - http://support.applitools.com/customer/portal/articles/2457891 
Getting Current/Baseline Images Manually - http://support.applitools.com/customer/portal/articles/2917372
Extend API features with EyesUtilities - http://support.applitools.com/customer/portal/articles/2913152