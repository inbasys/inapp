<html>
	<title>Salesforce Inapp message</title>
	<body>
	<script type='text/javascript'>
	function initEmbeddedMessaging() {
		try {
			console.log('Initializing Embedded Messaging...');
			embeddedservice_bootstrap.settings.language = 'en_US'; // Set language

			// Check if embeddedservice_bootstrap is loaded
			if (typeof embeddedservice_bootstrap !== 'undefined') {
				console.log('embeddedservice_bootstrap loaded successfully');
			} else {
				console.error('embeddedservice_bootstrap is not loaded');
			}

			// Event listener for Embedded Messaging readiness
			window.addEventListener("onEmbeddedMessagingReady", e => {
			    console.log("Embedded Messaging is ready!");
			    
			    // Set hidden pre-chat fields using API names with underscores
			    embeddedservice_bootstrap.prechatAPI.setHiddenPrechatFields({
			        "_firstName": "Inba",  // Use the API names with underscores
			        "_lastName": "Raj",
			        "_email": "inba@gmail.com",
			        "_subject": "Test prechat default values.",
					"Client_Type": "Test clienttype",	
					"FHA_Case_No":"7894561230",
					"Phone": "7418523698"
			    });

			    console.log("Prechat fields set:", {
			        "_FirstName": "Inba",
			        "_LastName": "Raj",
			        "_Email": "inba@gmail.com",
			        "_Subject": "Test prechat default values.",
					"Client_Type": "Test clienttype",	
					"FHA_Case_No":"7894561230",
					"Phone": "7418523698"
			    });
			});
			
			// Initialize the embedded messaging component
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
