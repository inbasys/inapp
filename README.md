<html>
	<title>Salesforce Inapp message</title>
<body>
<script type='text/javascript'>
function initEmbeddedMessaging() {
	try {
		embeddedservice_bootstrap.settings.language = 'en_US'; // For example, enter 'en' or 'en-US'

		window.addEventListener("onEmbeddedMessagingReady", e => {
		    embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
		        _firstName: "Inba"
				/*_lastName: "Raj",
				_email: "inba@gmail.com",
				_subject: "Test prechat default values."*/
		    });
		});

		embeddedservice_bootstrap.init(
			'00DSK0000000wbt',
			'InApp_Messaging',
			'https://hud4--hfdevp.sandbox.my.site.com/ESWInAppMessaging1721599833119',
			{
				scrt2URL: 'https://hud4--hfdevp.sandbox.my.salesforce-scrt.com'
			}
		);
	} catch (err) {
		console.error('Error loading Embedded Messaging: ', err);
	}
};
</script>
<script type='text/javascript' src='https://hud4--hfdevp.sandbox.my.site.com/ESWInAppMessaging1721599833119/assets/js/bootstrap.min.js' onload='initEmbeddedMessaging()'></script>
</body>
</html>
