# Identity Connect Delegated Auth Services 

Identity Connect can federeate like a champ...but did you know it can also perform Delegated Authentication?

All you need is to add one of these simple Apex Classes to your Org which can transform the Salesforce Delegated Authentication call into the REST Format used by Identity Connect.

##DelegatedAuthService

This is a simple DelegatedAuth Service.  To get started:

1. Copy the code and create DelegatedAuthService in your org
2. Configure the code so it points at your Identity Connect server.  Make sure you can get through any firewalls!
3. In a Site, or in the force.com Site that underlies your Community, enable the Site profile for this ApexClass.  This will expose an anonymous web service.  [https://developer.salesforce.com/blogs/developer-relations/2012/02/quick-tip-public-restful-web-services-on-force-com-sites.html](Read this for more information)
4. File a case with Salesforce Support, and have them enable Delegated Authentication 
5. Once enabled, configure your Delegated Auth url on Single Sign-On Settings as:  https://YOUR_SITE_OR_COMMUNITY_URL/services/apexrest/delegatedauth
6. Assign the Is Single Sign-On Enabled permission to any user's you'd like to use delegated auth


##MultiDelegatedAuthService

This is a DelegatedAuth Service that can split between multiple services..in case you have more than 1 AD deployment.  To get started:

1. Copy the code and create DelegatedAuthService in your org
2. Configure the code so it points at both your Identity Connect servers.  Make sure you can get through any firewalls!
3. Modify the code to support the best strategy for determining which server to route users to.  This implementation uses a custom picklist on user, but you might parse the email address and look at domain, go random, etc.
4. In a Site, or in the force.com Site that underlies your Community, enable the Site profile for this ApexClass.  This will expose an anonymous web service.  [https://developer.salesforce.com/blogs/developer-relations/2012/02/quick-tip-public-restful-web-services-on-force-com-sites.html](Read this for more information)
5. File a case with Salesforce Support, and have them enable Delegated Authentication 
6. Once enabled, configure your Delegated Auth url on Single Sign-On Settings as:  https://YOUR_SITE_OR_COMMUNITY_URL/services/apexrest/multidelegatedauth
7. Assign the Is Single Sign-On Enabled permission to any user's you'd like to use delegated auth

