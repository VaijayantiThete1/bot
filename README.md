<html>
	<head>
	<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

			embeddedservice_bootstrap.init(
				'00Ddq000001AfMH',
				'Live_Chat_Embedded_Deployment',
				'https://haporg--aicxdev.sandbox.my.site.com/ESWLiveChatEmbeddedDep1745212045719',
				{
					scrt2URL: 'https://haporg--aicxdev.sandbox.my.salesforce-scrt.com'
				}
			);
		} catch (err) {
			console.error('Error loading Embedded Messaging: ', err);
		}
	};
</script>
<script type='text/javascript' src='https://haporg--aicxdev.sandbox.my.site.com/ESWLiveChatEmbeddedDep1745212045719/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>

</head>
</html>
