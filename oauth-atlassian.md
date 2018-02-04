# OAuth
## Am Beispiel von Atlassian-Anwendungen (OAuth 1.0a)
---
# Allgemein
- Standard zur Autorisierung von Zugriffen auf Ressourcen
- OAuth
- 	- RFC-5849
- OAuth2
	- RFC-6479
	- vereinfacht den Zugriff
---
# OAuth 1.0a - Begriffe
- Consumer: Client
- Service Provider
- User
- Consumer Key und Secret
- Request Token und Secret
- Access Token und Secret
---

# OAuth 1.0a - Workflow
tbd

---
# OAuth 1.0a - 2-legged vs. 3-legged
- 3-legged beinhaltet Access Token und Secret
	- wird z. B. bei Web-Apps eingesetzt. Consumer Key/Secret hinterlegt der Betreiber der Web-App, Access Token und Secret der Benutzer der Web-App.
- 2-legged hat __kein__ Access Token und Secret
	- wird z. B. bei mobilen Twitter-Clients eingesetzt

---

# OAuth2 - Begriffe
tbd

---

# OAuth2 - Rollen
- Resource server - Jira
- Resource owner - mein Jira-Account
- Authorization server - Jira, Crowd
- Client - meine Anwendung, die auf Jira zugreift
---
# OAuth2 - Workflow

     +--------+                               +---------------+
     |        |--(A)- Authorization Request ->|   Resource    |
     |        |                               |     Owner     |
     |        |<-(B)-- Authorization Grant ---|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(C)-- Authorization Grant -->| Authorization |
     | Client |                               |     Server    |
     |        |<-(D)----- Access Token -------|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(E)----- Access Token ------>|    Resource   |
     |        |                               |     Server    |
     |        |<-(F)--- Protected Resource ---|               |
     +--------+                               +---------------+
siehe https://tools.ietf.org/html/rfc6749

---
# Beispiel
- Zugriff auf Atlassian-Dienste via OAuth 1.0a
	- OAuth2 nur für Connect-Anwendungen
- Atlassian bietet Beispielquellcode an
- jira-rest-client unterstützt nur Basic Auth

---
# getRequestToken

	public TokenSecretVerifierHolder getRequestToken() {
		// provider enthält u.a. consumerKey 
		// und consumerSecret und erzeugt den OAuthAccesor
		OAuthAccessor accessor = provider.getAccessor();
		OAuthClient oAuthClient = createOAuthClient();
		List<OAuth.Parameter> callBack;

		callBack = ImmutableList
            			.of(new OAuth.Parameter(OAuth.OAUTH_CALLBACK, provider.getCallback()));

		OAuthMessage message = oAuthClient.getRequestTokenResponse(accessor, "POST", callBack);

		TokenSecretVerifierHolder tokenSecretVerifier = new TokenSecretVerifierHolder(accessor.requestToken,
					accessor.tokenSecret, message.getParameter(OAUTH_VERIFIER));

		return tokenSecretVerifier;
	}
---

# swapRequestToken

	public String swapRequestTokenForAccessToken(String requestToken, String tokenSecret, String oauthVerifier) {
		OAuthAccessor accessor = provider.getAccessor();
		OAuthClient oAuthClient = createOAuthClient();
		accessor.requestToken = requestToken;
		accessor.tokenSecret = tokenSecret;
		OAuthMessage message = oAuthClient.getAccessToken(accessor, "POST",
					ImmutableList.of(new OAuth.Parameter(OAuth.OAUTH_VERIFIER, oauthVerifier)));

		return message.getToken();
	}
---

# makeAuthenticatedRequset

	public String makeAuthenticatedRequest(String url, String accessToken) {
		OAuthAccessor accessor = provider.getAccessor();
		OAuthClient oAuthClient = createOAuthClient();
		accessor.accessToken = accessToken;
		OAuthMessage response = oAuthClient.invoke(accessor, url, Collections.<Map.Entry<?, ?>>emptySet());

		return response.readBodyAsString();
	}
---

# Aufruf

	AtlassianOAuthProvider atlassianOAuthProvider = new AtlassianOAuthProvider(
    	"http://jira.atlassian.net",
		"my-consumer-key",
		"my-applications-private-key",
 		"http://localhost" /* or null */);

		AtlassianOAuthClient client = new AtlassianOAuthClient(atlassianOAuthProvider);
		TokenSecretVerifierHolder tokenSecretVerifierHolder = client.getRequestToken();

		// present user with the redirect
		System.out.println(
				"Go to " + atlassianOAuthProvider.getAuthorizeUrlForToken(tokenSecretVerifierHolder.getToken()));
		// after user has accepted, continue

		String accessToken = client.swapRequestTokenForAccessToken(tokenSecretVerifierHolder.getToken(),
				tokenSecretVerifierHolder.getSecret(), tokenSecretVerifierHolder.getVerifier());

		System.out.println("Storing your access token '" + accessToken
				+ "' in the database. Token is used for every request you are making to '"
				+ atlassianOAuthProvider.getBaseUrl() + "'");