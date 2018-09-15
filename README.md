# xeneta_technical_test
Code for Xeneta Automation Technical Test

# List of Test Cases
Media Resources Website
1) Check localization and cookie pop-up
2) Check navigation through the menu and elements for each section are present

Xeneta Demo Website
1) Check top and bottom menus are present, to-top button works and Youtube video is present and clickable
2) Check that fields are required and errors are shown when trying to submit the form without them
3) Check that form can be submited succesfully when all fields are properly filled

# Guide to try the tests
1) Download the Katalon_Studio_Windows_64.5.7.1 folder to your chosen path (Desktop recommended)
2) Go to the Command Line Prompt
3) Write the command below:
katalon -noSplash  -runMode=console -consoleLog -projectPath="\path\to\Katalon_Studio_Windows_64-5.7.1\Technical_Test_Xeneta\Technical_Test_Xeneta.prj" -retry=1 -retryFailedTestCases=true -testSuitePath="Test Suites/Xeneta Technical Test" -executionProfile="default" -browserType="Firefox"

3.1) Change -browserType="Firefox" to Chrome/Safari/Edge/IE to test the suite in different browsers


# Special Notes
1) The programming of the five test cases took aproximately 90 minutes, including the required mapping of the different DOM elements in Katalon Studio
2) Katalon Studio was chosen as the go-to framework because it's easy to use and really fast to set up, not requiring installation of any software.
3) For the required fields test case, the test checks that the different error messages appear, however, at the moment it does not check that every field has it's own error message. This can be done, however, it requires heavy programming as the websites are programmed using Reactjs, which changes the classes and IDs of the DOM elements on every execution of the website. This is not a problem for the fields of the form as they can be detected by using the "Start with" condition. However, in the case of the errors, they do not have an ID, and even if the class could be used, the important section of the class is shared the fields and would require the use of regular expressions in order to detect the class for the errors but not for the input fields.
4) The majority of the test steps are change-agnostic, which means, that independently of the UI changes the website suffers, as long as the base for the class, ID and href do not change, the tests will still be able to locate the DOM elements. 
5) There are, however, a few DIV which do not have a class or ID that are located through the text it has. A "contains" condition has been used in order to make the control as wide as possible, but if the text would be changed drastically the location would fail. Same behaviour would happen with images on the Media Resources website. If the image names change, the location wouldn't be possible. This is something that cannot be avoided and requires communication between the development and the testing team so the tests can be updated as soon as possible in case this events would happen.
