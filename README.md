<html>
	<head>
		
	<script type='text/javascript'>
	document.addEventListener("message", (event) => {
system.debug('Inside event');
if ((event.data.method === "EMBEDDED_MESSAGING_DISPATCH_EVENT_TO_HOST" && event.data.data.eventDetails.conversationEntry && event.data.data.eventDetails.conversationEntry.entryPayload)) {

let payload = JSON.parse(event.data.data.eventDetails.conversationEntry.entryPayload)
system.debug('Payload: '+payload);
    if( payload.abstractMessage && payload.abstractMessage.choices) {

postIframeDisable();

}

    else if(payload.abstractMessage && payload.abstractMessage.choicesResponse){

       postIframeEnable();

    }

}

});


//posting message to enable user input

function postIframeEnable(){

var iframe = document.getElementById("embeddedMessagingFrame");

   iframe.contentWindow.postMessage('InputEnable');

}
//posting message to disable user input

function postIframeDisable(){

var iframe = document.getElementById("embeddedMessagingFrame");

   iframe.contentWindow.postMessage('InputDisable');

}
	function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

			embeddedservice_bootstrap.init(
				'00DRt000009ECCE',
				'Vaijayanti_Test_Deployment',
				'https://haporg--pocagent.sandbox.my.site.com/ESWVaijayantiTestDeploy1744863440015',
				{
					scrt2URL: 'https://haporg--pocagent.sandbox.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
 //event listener which listens to every message/event from the Iframe


</script>
<script type='text/javascript' src='https://haporg--pocagent.sandbox.my.site.com/ESWVaijayantiTestDeploy1744863440015/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'>
</script>


</head>
</html>
