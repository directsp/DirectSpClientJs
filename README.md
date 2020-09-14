# DirectSpClientJs
DirectSp client for JavaScript

## Usage

1. Install by NPM
``` NPM
npm i @directsp/client-js
```

2. Create and intialize object
```javascript
import { directSp } from "../node_modules/@directsp/client-js";

// Creating a global DirectSpClient object
window.dspClient = new directSp.DirectSpClient({
  resourceApiUri: "http:/your_directsp_host_url/api",
  isLogEnabled: true,
  isUseAppErrorHandler: true
});

// Initializing the object
dspClient.init();

// Handle authentication if any
// update this property as soon as your authorization provider gives you a new token
dspClient.authHeader = "a bearer authorization token such as google user token";

3. Invoke procedures

```javascript
// without options
dspClient.invoke("MyMethod", { param1: "value1", param2: "value2" })
  .then(data => {
    console.log(data);
    console.log(data.returnValue);
    console.log(data.outParam1);
    console.log(data.outParam2);
    console.log(data.recordset);
  });

// with options
dspClient.invoke("MyMethod", { param1: "value1", param2: "value2" }, { recordIndex: 0, recordCount: 10 })
  .then(data => {
    console.log(data);
  });
```
## Authentication
You can bypass authentication system by setting auth to null

## Runtime API Help
in your browser console just run
```javascript
dspClient.help()
```
