# jQuery-Electron fix
When using Electron and UI5, there are som issues with loading jQuery. Fix this using the following snippet:

```html
<!-- Insert this line above script imports  -->
<script>if (typeof module === 'object') {window.module = module; module = undefined;}</script>

<!-- normal script imports etc  -->
<script id='sap-ui-bootstrap' 
    src='../resources/sap-ui-core.js'
    data-sap-ui-theme='sap_belize'  
    data-sap-ui-libs='sap.m'
    data-sap-ui-compatVersion='edge'
    data-sap-ui-bindingSyntax='complex'
    data-sap-ui-resourceroots='{
        "<namespace>": "./"
    }'
    data-sap-ui-preload='async'></script>

<!-- Insert this line after script imports -->
<script>if (window.module) module = window.module;</script>
```


### Source: [Electron: jQuery is not defined](https://stackoverflow.com/questions/32621988/electron-jquery-is-not-defined/37480521#37480521)