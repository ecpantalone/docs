# K6 + Cypress for load testing
    K6 is a tool we can pair with Cypress to record our automated tests, and then run via K6 with multiple virtual users.  
    To get your environment set up to use K6 to record your cypress test:
        - `brew install k6`
        - Download K6 recorder Chrome extension 
            - go to https://chrome.google.com/webstore and search for CRX Extractor/Downloader and install it  
            - go to https://chrome.google.com/webstore and search for K6 Browswer Recorder, don't install  
            - While you're on the K6 extension page above, use the CRX Extractor extension you just installed on Chrome to download the K6 browser extension as a .zip file. Save and extract wherever is convenient (I chose my desktop)  

        - go to https://app.k6.io/tests/new/cli and copy the script in "Log into your account", it should look something like `k6 login cloud -t abc123.....`
        - paste that script you just copied into the terminal window where you will run your Cypress tests in the gui, and then run the `yarn cypress-gui` command to open the Cypress gui.

        The above steps make it so the Chrome instance that runs Cypress is including the K6 recording extension.  

    To record a test:
        - after you run `yarn cypress-gui` to open the Cypress gui, and choose a test or set of tests to run, you will see the `Tests Loading` animation as well as the purple K6 logo where Chrome extensions are displayed in the top right browser toolbar.
        - click the K6 extension in the Cypress Chrome window and choose `Begin Recording`  
        - once the test has finished, end the recording  
        - visit the K6 website and the test will be available on the dashboard where you can create and edit it in the js editor on screen
