<html>
	<style type='text/css'>
	.embeddedMessagingConversationButtonWrapper .embeddedMessagingConversationButton {
		background-color: #0081A1;
		font-family: "Chivo", sans-serif;
	}
	.embeddedMessagingConversationButtonWrapper .embeddedMessagingConversationButton:focus {
		outline: 1px solid #0081A1;
	}
	
        .slds-icon-utility-minimize-window{
    		zoom: 120%;
	 }       
    	 .slds-icon-utility-close{
          	zoom: 120%;
     	  }
    
    	 .slds-form-element__label{
        	font-size:1.5ch;
       	}
	.custom-header {
		color: black;
		font-size: 2em;
		text-align: center;
		margin: 20px 0;
	}
	.embedded-messaging {
		--eswHeight: 500px; /* Change height here */
	}
	
	/* Override max-height to increase the height of the chat window */
@media only screen and (min-width: 48em) {
    .embedded-messaging > .embeddedMessagingFrame[class~="isMaximized"] {
        max-height: 200vh !important; /* Increase the max-height */
    }
}

</style>

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
      		 iframe.contentWindow.onload = function(){
            		console.log("I am loaded");
	      		iframe.contentWindow.postMessage('InputDisable');
        	};
		
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
