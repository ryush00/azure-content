<properties pageTitle="Get started with authentication (Windows Store) | Mobile Dev Center" metaKeywords="authentication, FAcebook, GOogle, Twitter, Microsoft Account, login" description="Learn how to use Mobile Services to authenticate users of your Windows Store app through a variety of identity providers, including Google, Facebook, Twitter, and Microsoft." metaCanonical="" services="mobile" documentationCenter="Mobile" title="Get started with authentication in Mobile Services" authors="Glenn Gailey"  solutions="" writer="glenga" manager="" editor=""  />

# Get started with authentication in Mobile Services

<div class="dev-center-tutorial-selector sublanding"> 
	<a href="/en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-dotnet-get-started-users" title="Windows Store C#">Windows Store C#</a>
	<a href="/en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-javascript-get-started-users" title="Windows Store JavaScript" class="current">Windows Store JavaScript</a>
	<a href="/en-us/documentation/articles/mobile-services-dotnet-backend-windows-phone-get-started-users" title="Windows Phone">Windows Phone</a>
	<!--<a href="/en-us/documentation/articles/mobile-services-dotnet-backend-ios-get-started-users" title="iOS">iOS</a>
	<a href="/en-us/documentation/articles/mobile-services-dotnet-backend-android-get-started-users" title="Android">Android</a>-->
</div>

<div class="dev-center-tutorial-subselector">
	<a href="/en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-javascript-get-started-users/" title=".NET backend" class="current">.NET backend</a> | 
	<a href="/en-us/documentation/articles/mobile-services-windows-store-javascript-get-started-users/"  title="JavaScript backend">JavaScript backend</a>
</div>

This topic shows you how to authenticate users in Windows Azure Mobile Services from your app. In this tutorial, you add authentication to the quickstart project using an identity provider that is supported by Mobile Services. After being successfully authenticated and authorized by Mobile Services, the user ID value is displayed.

This tutorial walks you through these basic steps to enable authentication in your app:

1. [Register your app for authentication and configure Mobile Services]
2. [Restrict table permissions to authenticated users]
3. [Add authentication to the app]

This tutorial is based on the Mobile Services quickstart. You must also first complete the tutorial [Get started with Mobile Services]. 

>[WACOM.NOTE]This tutorial demonstrates the basic method provided by Mobile Services to authenticate users by using a variety of identity providers. This method is easy to configure and supports multiple providers. However, this method also requires users to log-in every time your app starts. To instead use Live Connect to provide a single sign-on experience in your Windows Store app, see the topic [Single sign-on for Windows Store apps by using Live Connect].

<h2><a name="register"></a><span class="short-header">Register your app</span>Register your app for authentication and configure Mobile Services</h2>

[WACOM.INCLUDE [mobile-services-register-authentication](../includes/mobile-services-register-authentication.md)] 

<ol start="5">
<li><p>(Optional) Complete the steps in <a href="/en-us/documentation/articles/mobile-services-how-to-register-store-app-package-microsoft-authentication/">Register your Windows Store app package for Microsoft authentication</a>.</p>

    <div class="dev-callout"><b>Note</b>
	<p>This step is optional because it only applies to the Microsoft Account login provider. When you register your Windows Store app package information with Mobile Services, the client is able to re-use Microsoft Account login credentials for a single sign-on experience. If you do not do this, your Microsoft Account login users will be presented with a login prompt every time that the login method is called. Complete this step when you plan to use the Microsoft Account identity provider.</p>
    </div>
</li>
</ol>
<h2><a name="permissions"></a><span class="short-header">Restrict permissions</span>Restrict permissions to authenticated users</h2>

[WACOM.INCLUDE [mobile-services-restrict-permissions-dotnet-backend](../includes/mobile-services-restrict-permissions-dotnet-backend.md)] 

<ol start="3">
<li><p>In Visual Studio 2013, open the project that you created when you completed the tutorial <a href="/en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-dotnet-get-started/">Get started with Mobile Services</a>.</p></li> 
<li><p>Press the F5 key to run this quickstart-based app; verify that an unhandled exception with a status code of 401 (Unauthorized) is raised after the app starts.</p>
   
   	<p>This happens because the app attempts to access Mobile Services as an unauthenticated user, but the <em>TodoItem</em> table now requires authentication.</p></li>
</ol>

Next, you will update the app to authenticate users before requesting resources from the mobile service.

<h2><a name="add-authentication"></a><span class="short-header">Add authentication</span>Add authentication to the app</h2>

[WACOM.INCLUDE [mobile-services-windows-store-javascript-authenticate-app](../includes/mobile-services-windows-store-javascript-authenticate-app.md)] 



<!-- Anchors. -->
[Register your app for authentication and configure Mobile Services]: #register
[Restrict table permissions to authenticated users]: #permissions
[Add authentication to the app]: #add-authentication
[Next Steps]:#next-steps


<!-- URLs. -->
[Submit an app page]: http://go.microsoft.com/fwlink/p/?LinkID=266582
[My Applications]: http://go.microsoft.com/fwlink/p/?LinkId=262039
[Live SDK for Windows]: http://go.microsoft.com/fwlink/p/?LinkId=262253
[Single sign-on for Windows Store apps by using Live Connect]: /en-us/documentation/articles/mobile-services-windows-store-dotnet-single-sign-on
[Get started with Mobile Services]: /en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-javascript-get-started/
[Get started with data]: /en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-javascript-get-started-data/
[Get started with authentication]: /en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-javascript-get-started-users/
[Get started with push notifications]: /en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-javascript-get-started-push/
[Authorize users with scripts]: /en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-javascript-authorize-users-in-scripts
[JavaScript and HTML]: /en-us/documentation/articles/mobile-services-dotnet-backend-windows-store-dotnet-get-started-users/

[Windows Azure Management Portal]: https://manage.windowsazure.com/
[Mobile Services .NET How-to Conceptual Reference]: /en-us/develop/mobile/how-to-guides/work-with-net-client-library
[Register your Windows Store app package for Microsoft authentication]: /en-us/documentation/articles/mobile-services-how-to-register-store-app-package-microsoft-authentication