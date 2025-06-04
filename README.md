<html>
	<head>

window.addEventListener("message", (event) => {
console.log('Hi');
}

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
