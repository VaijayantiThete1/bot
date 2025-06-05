<html>
	<head>
<script>

  
window.addEventListener("message", (event) => {

if ((event.data.method === "EMBEDDED_MESSAGING_DISPATCH_EVENT_TO_HOST" && event.data.data.eventDetails.conversationEntry && event.data.data.eventDetails.conversationEntry.entryPayload)){
	console.log('Inside if 1');
 	let payload = JSON.parse(event.data.data.eventDetails.conversationEntry.entryPayload);
 	if(payload.abstractMessage && payload.abstractMessage.choices) {

		console.log('Inside if 2');
  		var iframe = document.getElementById("embeddedMessagingFrame");
    		console.log('iframe1: '+iframe);
   		iframe.disabled = true;
     		console.log('isdisable: '+iframe.disabled);
		iframe.style.display = 'block';
	}
 	else if(payload.abstractMessage && payload.abstractMessage.choicesResponse){
       		console.log('Inside if 3');
		var iframe = document.getElementById("embeddedMessagingFrame");
  		iframe.contentWindow.postMessage('InputEnable');

    	}
}

});

</script>
	</head>
	<body>
		<script type='text/javascript'>
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
</script>
<script type='text/javascript' src='https://haporg--pocagent.sandbox.my.site.com/ESWVaijayantiTestDeploy1744863440015/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>


	</body>
</html>
