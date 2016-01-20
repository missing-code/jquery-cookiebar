# jQuery CookieBar Plugin

On the 26th of May 2012, the EU government decided it was necessary for every website available inside the EU to have to give visitors the option to allow or disable cookies. While most people saw this as unnecessary and a disruption to collecting analytical data, etc, the EU law was passed. One of the EU's steps towards ruining the internet.

But rather than simply refuse to comply and potentially face consequences in the future, a lot of website owners and developers took the step of implementing code on their websites to give users the option to enable or disable cookies.

## Introduction

The Cookie Bar plugin creates a small bar at the top or bottom of the website with a short message about cookies and accept, decline, and privacy policy buttons.

Once a user has made the decision to either accept or decline, the Cookie Bar slides up, then disappears.

The Cookie Bar can be set up to work in a variety of ways. By default, it uses assumed consent. This means that when a user visits the website, cookies can be set as normal with no interruption. The Cookie Bar is still displayed to provide the user with options for cookies.

It can also be set up to assume refusal. So when a user visits the website, until they press the accept button on the Cookie Bar, no cookies should be set.

You can specify which buttons show on the Cookie Bar. The default is to show the accept and privacy policy buttons and no decline button. This way, assumed consent is used, and the user cannot opt out of cookies. If the user is unhappy about the use of cookies, they can simply leave the website.

The Cookie Bar is also very easy to style. There are just 9 lines of CSS code in total. Changing the heights, widths, background colours, etc. is very quick and easy meaning it can fit in with the website design and colour scheme.

## Installing

To start, download the zip file containing the Cookie Bar plugin, a CSS file and example HTML document. Upload the javascript and CSS files to your website and add them between your head tags. Make sure to download the latest version of jQuery if your website does not already include it.

You will also need to initialise the Cookie Bar, which can be done with the following code (Make sure if you already use $(document).ready() that you only copy what you need of below so you don't have too many $(document).ready()'s).

	$(document).ready(function(){
	  $.cookieBar();
	});

Refresh your website, and the Cookie Bar should appear!

A basic setup may look like the following:

	<script type="text/javascript" src="/your-js-folder/jquery.js"></script> 
	<script type="text/javascript" src="/your-js-folder/jquery.cookiebar.js"></script> 
	<script type="text/javascript"> 
	  $(document).ready(function(){
	     $.cookieBar();
	  });
	</script>

**If the cookiebar does not show, check for any javascript errors.**

**If the cookiebar continues to show after accepting/declining, make sure to remove the option "forceShow" from your code, or set it to "false".**

## Disabling Google Analytics and other cookies

If a user chooses to disable cookies (If you give them that option), you need to make sure that scripts such as Google Analytics need to be disabled.

This can be done by wrapping the code in a simple if statement.

	if(jQuery.cookieBar('cookies')){
	  //Google Analytics or other code here
	}
	
## Options

There are a number of options allowing you to customise how the plugin works:

	message: 'We use cookies to track usage and preferences',
	acceptButton: true,
	acceptText: 'I Understand',
	acceptFunction: null,
	declineButton: false,
	declineText: 'Disable Cookies',
	declineFunction: null,
	policyButton: true,
	policyText: 'Privacy Policy',
	policyURL: '/privacy-policy/',
	autoEnable: true,
	acceptOnContinue: false,
	acceptOnScroll: false,
	acceptAnyClick: false,
	expireDays: 365,
	renewOnVisit: false,
	forceShow: false,
	effect: 'slide',
	element: 'body',
	append: false,
	fixed: false,
	bottom: false,
	zindex: '',
	domain: 'www.example.com',
	referrer: 'www.example.com'