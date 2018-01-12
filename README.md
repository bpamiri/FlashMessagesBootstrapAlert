# FlashMessages Bootstrap - CFWheels 2.0 Plugin
This plugin modifies the default HTML block generated by the builtin CFWheels **#flashMessages()#** function and modifies it to be compatible with the markup needed by Twitter Bootstrap Alert elements.

## Installation via CommandBox

To install this plugin via CommandBox simply navigate to the root of your project and issue the following command in the CommandBox window.

~~~Bash
$ box install cfwheels-flashmessages-bootstrap
~~~

## Usage/Examples

This plugin handles three different cases of alerts:
* If the flash key name is one of the sandard Twitter Bootstrap Alert types of **info**, **success**, **warning**, or **danger**, a Twitter Bootstrap compatible class of either **alert-info**, **alert-success**, **alert-warning**, or **alert-danger** will be used to create the markup block according to the flash key name.
* In addition to the standard Twitter Bootstrap Alert types mentioned above, this plugin also will look for a Flash key of **error** and convert that to a Twitter Bootstrap class of **alert-danger**.
* This plugin also has a catch all wildcard feature that will convert any other remainig Flash keys not handled by the cases above to the standard Twitter Bootstrap class of **alert-info**.

To use this plugin simply add the following code to your view or layout file.
~~~ColdFusion
<cfoutput>
  #flashMessages()#
</cfoutput>
~~~

## Configuration

This plugin modifies the default HTML block generated by the builtin CFWheels **#flashMessages()#** function and modifies it to be compatible with the markup needed by Twitter Bootstrap Alert elements.

In order for the newly modified markup block to be rendered properly you need to make sure that you have configured Twitter Bootstrap properly in your view or layout file. Here is an example of how to configure your layout.cfm file in order to render these alert properly.

~~~ColdFusion
<!--- Place HTML here that should be used as the default layout of your application. --->
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <cfoutput>#csrfMetaTags()#</cfoutput>

    <!-- Bootstrap -->
	<!-- Latest compiled and minified CSS -->
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

	<!-- Optional theme -->
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap-theme.min.css" integrity="sha384-rHyoN1iRsVXV4nD0JutlnGaslCJuC7uwjduW9SVrLvRYooPp2bWYgmgJQIXwl/Sp" crossorigin="anonymous">

    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.3/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->
  </head>
  <body>
		<cfoutput>
		#flashMessages()#
		#includeContent()#
		</cfoutput>

	    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
	    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
	    <!-- Include all compiled plugins (below), or include individual files as needed -->
		<!-- Latest compiled and minified JavaScript -->
		<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>    
  </body>
</html>
~~~

## Uninstallation

To uninstall this plugin, simply delete the /plugins/FlashMessagesBootstrap-x.x.x.zip file.

## Credits

This plugin was created by Peter Amiri. Please feel free to submit an issue or fork this plugin.
