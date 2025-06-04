<html>
	<head>
<script>

  window.addEventListener("message", (event) => {
  let method1 = event.data.method;
  console.log('Method1:'+method1);
  let method2 = event.data.data.eventDetails.conversationEntry;
  let method3 = event.data.data.eventDetails.conversationEntry.entryPayload;
  console.log('Method2:'+method2);
  console.log('Method3:'+method3);
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
