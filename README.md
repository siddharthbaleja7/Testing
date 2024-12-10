# Smart Wearable Companion App - Login and Onboarding Test Cases

## 1. Positive Test Cases

### 1.1 Google Sign-In
- **Test Case ID**: LO_001
- **Description**: Verify successful login using a valid Google account
- **Steps**:
  1. Open app
  2. Select Google Sign-In option
  3. Choose a valid Google account
  4. Authorize app permissions
- **Expected Result**: User is successfully logged in and directed to Bluetooth pairing screen

### 1.2 Apple ID Sign-In
- **Test Case ID**: LO_002
- **Description**: Verify successful login using a valid Apple ID
- **Steps**:
  1. Open app
  2. Select Apple Sign-In option
  3. Choose a valid Apple ID
  4. Authorize app permissions
- **Expected Result**: User is successfully logged in and directed to Bluetooth pairing screen

### 1.3 Bluetooth Pairing
- **Test Case ID**: LO_003
- **Description**: Verify successful Bluetooth pairing of wearable with phone
- **Precondition**: User is logged in via Google/Apple
- **Steps**:
  1. Ensure Bluetooth is enabled on phone
  2. Put wearable in pairing mode
  3. Select wearable from available devices
  4. Complete pairing process
- **Expected Result**: Wearable is successfully paired, user is taken to home screen

## 2. Negative/Error Test Cases

### 2.1 Invalid/Expired Social Credentials
- **Test Case ID**: LO_004
- **Description**: Verify app behavior with invalid social login credentials
- **Steps**:
  1. Attempt login with expired or revoked social account
  2. Attempt login with incorrect account credentials
- **Expected Result**: 
  - Appropriate error message displayed
  - Option to retry login or choose another account
  - No unauthorized access granted

### 2.2 No Internet Connection
- **Test Case ID**: LO_005
- **Description**: Verify app behavior during login with no internet connectivity
- **Steps**:
  1. Disable internet connection
  2. Attempt social login (Google or Apple)
- **Expected Result**:
  - Clear error message indicating "No internet connection" or "Unable to connect"
  - Option to retry login after reconnecting
  - No login attempt should be made without connectivity

### 2.3 Bluetooth Pairing Failures
- **Test Case ID**: LO_006
- **Description**: Verify handling of Bluetooth pairing failures
- **Scenarios**:
  a. Wearable not in pairing mode
  b. Bluetooth not enabled on phone
  c. Wearable out of range
  d. Multiple pairing attempts
- **Expected Result**:
  - Specific error messages for each scenario
  - Clear instructions for resolving pairing issues
  - Option to retry pairing

## 3. Edge Cases

### 3.1 Multiple Device Management
- **Test Case ID**: LO_007
- **Description**: Verify behavior when attempting to pair multiple devices
- **Steps**:
  1. Pair first wearable successfully
  2. Attempt to pair a second wearable
- **Expected Result**:
  - Clear options for device management
  - Ability to switch or add new devices
  - No data conflict

### 3.2 Privacy and Permissions
- **Test Case ID**: LO_008
- **Description**: Verify handling of permission denials during login
- **Steps**:
  1. Start social login
  2. Deny certain app permissions
- **Expected Result**:
  - Clear communication about required vs optional permissions
  - Ability to modify permissions
  - Graceful handling of partial permission grants

## 4. Security Test Cases

### 4.1 Authentication Token Management
- **Test Case ID**: LO_009
- **Description**: Verify secure handling of authentication tokens
- **Validation Points**:
  - Tokens are not stored in plain text
  - Tokens are securely encrypted
  - Tokens are invalidated after logout
  - Token refresh mechanism works correctly

## 5. Performance Test Cases

### 5.1 Login and Pairing Speed
- **Test Case ID**: LO_010
- **Description**: Measure login and pairing process performance
- **Performance Metrics**:
  - Social login completion time
  - Bluetooth pairing time
  - Overall process duration
- **Acceptable Thresholds**:
  - Social login: < 5 seconds
  - Bluetooth pairing: < 10 seconds
  - Total process: < 20 seconds

