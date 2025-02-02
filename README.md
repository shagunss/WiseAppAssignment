# Selenium Automation Test Script

This README explains how to set up, configure, and run the provided Selenium automation test script.

## Prerequisites

1. **Python Installed**
   - Ensure you have Python 3.8 or higher installed on your machine.
   - Verify installation by running:
     ```bash
     python --version
     ```

2. **Google Chrome Installed**
   - Download and install the latest version of Google Chrome.

3. **ChromeDriver Installed**
   - Download the compatible version of ChromeDriver for your installed version of Google Chrome from [ChromeDriver](https://chromedriver.chromium.org/downloads).
   - Add ChromeDriver to your system PATH or specify its location when initializing the WebDriver.

4. **Install Required Python Packages**
   - Install Selenium and other dependencies using `pip`:
     ```bash
     pip install selenium
     ```

## Script Configuration

### Test Script Overview
The script automates the following steps:
1. Logging into a web application using a mobile number and OTP.
2. Navigating to a specific classroom and opening the "Live Sessions" tab.
3. Scheduling a new live session and verifying the session details.

### Key Variables
- **Web URL:** The application URL is `https://staging-web.wise.live`.
- **Phone Number:** Replace `1111100000` in the script with the desired test phone number.
- **OTP Code:** Replace `0000` with the correct OTP for login.

### Script Components
- **Login:** Handles mobile login and OTP validation.
- **Classroom Navigation:** Opens the "Group courses" section and selects the desired classroom.
- **Live Session Scheduling:** Adds a new live session and verifies details like session time and hosted-by information.

## How to Run the Script

1. **Set Up ChromeDriver Path**
   - Ensure ChromeDriver is in your system PATH or modify the following line to include its location:
     ```python
     driver = webdriver.Chrome(executable_path='path/to/chromedriver')
     ```

2. **Run the Script**
   - Save the script as `test_script.py`.
   - Run the script using the command:
     ```bash
     python test_script.py
     ```

3. **Inspect and Debug**
   - If an error occurs, the script prints a detailed traceback to the console for debugging purposes.
   - The browser will remain open until you press `Enter` to exit.

## Expected Outputs

1. **Login Validation:**
   - Asserts that "Testing Institute" appears on the page after login.

2. **Classroom Navigation:**
   - Verifies the presence of "Classroom for Automated testing" on the page.

3. **Live Session Details:**
   - Asserts that the session time is "Sun, 10:00 pm - 11:00 pm".
   - Confirms that the session is "HOSTED BY WISE TESTER".

4. **Success Messages:**
   - On successful execution, the script prints the following:
     ```plaintext
     Assertion passed: Text matches 'Live session'
     Assertion passed: Text matches 'HOSTED BY WISE TESTER'
     Assertion passed: Text matches 'Sun, 10:00 pm - 11:00 pm'
     ```

## Troubleshooting

1. **Mismatch Errors:**
   - If an assertion fails, verify the XPath locators and the expected text in the application.

2. **Element Not Found Errors:**
   - Ensure that all dynamic elements have loaded by increasing the WebDriver wait time.

3. **ChromeDriver Issues:**
   - Ensure ChromeDriver matches your installed Chrome version.

## Notes

- **Modify OTP Handling:** If OTP handling changes (e.g., dynamic generation), update the `otp_code` variable accordingly.
- **Environment Compatibility:** This script is tested with ChromeDriver and Chrome on Windows. For other operating systems, ensure compatibility.

## License
This script is provided as-is for educational and testing purposes.

