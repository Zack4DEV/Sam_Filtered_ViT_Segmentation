---
title: "PayPal Developer • NVP-SOAP Legacy -> BrainTree SDK"
datePublished: Sat Jun 01 2024 00:30:07 GMT+0000 (Coordinated Universal Time)
cuid: cmcrwscry000302jr6bkl3wod
slug: paypal-developer-nvp-soap-legacy-braintree-sdk-8276c8dc2f0f

---

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1751820654226/a5f9b2d2-1538-48d5-b59a-9b75e2823833.jpeg)

The migration of PayPal’s NVP-SOAP API to the BrainTree SDK is a significant change, delivering enhanced functionality and modern API standards.

\* NVP-SOAP Legacy — Documents: [https://developer.paypal.com/api/nvp-soap](https://developer.paypal.com/api/nvp-soap)

\* BrainTree JS SDK — Documents: [https://developer.paypal.com/sdk/js/](https://developer.paypal.com/sdk/js/)

\* NVP-SOAP to BrainTree SDK — Migration Steps:

\-Understand current usage: Identify all operations you currently perform with the NVP-SOAP API.

\-Configure a BrainTree account: necessary, a BrainTree account, correctly configured on the chosen environment.

\-Install BrainTree SDK: Integrate BrainTree SDK into the project.

\- Update payment logic: Replace NVP-SOAP API calls with BrainTree SDK methods. This should involve updating the backend code to create and manage transactions through BrainTree.

\-Example: Node.js custom transaction

— using npm: npm install braintree + Load .js script:<script src=”[https://js.braintreegateway.com/web/3.78.1/js/client.min.js](https://js.braintreegateway.com/web/3.78.1/js/client.min.js)"></script>

— transaction to create:  
/\*\*  
const braintree = require(‘braintree’);

const gateway = new braintree.BraintreeGateway({  
 environment: braintree.Environment.Sandbox,  
 MerchantId: ‘your\_merchant\_id’,  
 publicKey: ‘your\_public\_key’,  
 privateKey: ‘your\_private\_key’  
});

gateway.transaction.sale({  
 amount: ‘10.00’,  
 paymentMethodNonce: ‘client-nonce’,  
 options: {  
 submitForSettlement: true  
 }  
}, (error, result) => {  
 if (result.success) {  
 console.log(‘Transaction ID: ‘ + result.transaction.id);  
 } other {  
 console.error(result.message);  
 }  
});  
\*/

— Front-end integration:  
/\*\*  
<script src=”[https://js.braintreegateway.com/web/dropin/1.31.1/js/dropin.min.js](https://js.braintreegateway.com/web/dropin/1.31.1/js/dropin.min.js)"></script>  
<div id=”dropin-container”></div>  
<button id=”submit-button”>Request a payment method</button>  
<script>  
 braintree.dropin.create({  
 authorization: ‘YOUR\_CLIENT\_AUTHORIZATION’,  
 container: ‘#dropin-container’  
 }, function (createErr, instance) {  
 document.querySelector(‘#submit-button’).addEventListener(‘click’, function() {  
 instance.requestPaymentMethod(function(error, payload) {  
 // Send payload.nonce to your server  
 });  
 });  
 });  
</script>

\*/  
Last updated April 6, 2022 PayPal NVP-SOAP Developer is migrating to BrainTree Js SDK and working to support all custom transactions.

What characterizes a PayPal developer profile is that it is always available for other technologies such as Donate SDK or BrainTree Graph.  
#Rest #Node #PayPal-Developer #Graph #SDK #BrainTree #Alternative-NVP-SOAP #Event-Instant