# Expo Constants.deviceId Undefined in Background Tasks

This repository demonstrates a bug where `Constants.deviceId` returns `undefined` when accessed within an Expo background task or service worker.  The issue is resolved by using the `AppRegistry` to register a background task and then accessing the device ID within that task using a different approach (in this case, reading from AsyncStorage which should have the ID stored in advance). 

## How to Reproduce

1. Clone this repository.
2. Run `npm install`.
3. Run the app on a device or emulator.
4. Attempt to perform a background task.  Observe that the `deviceId` logged in the background task is `undefined` (in `bug.js`).
5. Refer to `bugSolution.js` for a corrected implementation.