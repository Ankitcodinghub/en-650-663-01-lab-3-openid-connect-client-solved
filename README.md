# en-650-663-01-lab-3-openid-connect-client-solved
**TO GET THIS SOLUTION VISIT:** [EN.650.663-01 Lab 3-OpenID Connect Client Solved](https://www.ankitcodinghub.com/product/en-650-663-01-lab-3-openid-connect-client-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;94919&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;0&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;0&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;0\/5 - (0 votes)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;EN.650.663-01 Lab 3-OpenID Connect Client Solved&quot;,&quot;width&quot;:&quot;0&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 0px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            <span class="kksr-muted">Rate this product</span>
    </div>
    </div>
<h1>Description</h1>
For this project we will add a third-party OpenID Connect button to our login page. This will allow us to, for example, login with Google. You may choose any ID provider that you like. Instructions for getting the client ID and client secret for Google are listed here, if you decide to go that way: <a href="https://developers.google.com/identity/protocols/OpenIDConnect">https://developers.google.com/identity/protocols/OpenIDConnect</a>. Note that these instructions are great for getting keys and IDs, but not so great for actually implementing your login button and redirect URI. Better instructions will be given for that below.

&nbsp;

Do explore just a little bit. You might want to try using Amazon Cognito, or Auth0, or Okta, or some other identity provider. Any of these are fine. Be aware that your redirect URI should probably be your <strong>deployed application URL</strong>. If you set one up for localhost (which can work, since the browser is making the requests), you will actually need a <em>separate</em> client ID. Just be careful of that and pick one.

<h1>Create a Client ID and Secret</h1>
Whatever provider you use, you will need to do some setup before starting. You need to get an account with them and find a way to get a <strong>Client ID</strong> and a <strong>Client Secret</strong>.

&nbsp;

You will be asked to provide

<ul>
<li>Application Name: a string that identifies your application. Will go into your request URL</li>
<li>Redirect URI: this should be “https://yourserver.appspot.com/oidcauth”.</li>
</ul>
&nbsp;

Your URL <strong>can be different</strong> if you want it to be, but I’ll assume it’s `/oidcauth’ for the discussion here just to make it concrete. Whatever you use, <em>it has to be what you registered</em> with the ID provider.

&nbsp;

There are many free providers, or providers with free trials. Use one of those.

&nbsp;

If you go with Google, the instructions are here for getting a Client ID and Secret: <a href="https://developers.google.com/identity/protocols/OpenIDConnect">https://developers.google.com/identity/protocols/OpenIDConnect</a>

&nbsp;

Once you have a Client ID and Client Secret, it’s time to implement OpenID Connect!

<h1>First Things First</h1>
What do you do with your client secret? You’ll need to put it somewhere, but where?

&nbsp;

The answer is definitely <strong><em>not</em></strong> “in your code”. That is a terrible location for secrets, largely because <em>your code is rarely actually secret</em>. So, no secrets in your code.

&nbsp;

There are key management services like <a href="https://cloud.google.com/kms/">https://cloud.google.com/kms/</a>, but those might be overkill for a lab. Instead, for this lab you can store your secret in the datastore. That, at least, can only be viewed by an administrator, and you won’t leak the secret to either the code or the browser.

&nbsp;

In my case, I created a new kind and key name like this:

After you create that entity, you can click on it to see its key, and use that to access it from your code. If you follow the above example, the key screen (after selecting the new entity) looks like this:

&nbsp;

Once it’s in there, you can easily get it using the same exact key:

<table>
<tbody>
<tr>
<td width="624">client = datastore.Client()

secret = client.get(client.key(‘secret’, ‘oidc’))[‘client-secret’]</td>
</tr>
</tbody>
</table>
&nbsp;

Now we’re ready. We have a place to store our client secret that is protected behind a login (the admin page after deployment will only let <strong>you</strong> view the datastore), and it is not in code. Cool.

<h1>Make a Button, use 3-Legged OAuth Flow</h1>
Your button or link will basically send the user to an identity provider site. You need a CSRF authentication token (called “state” in the standard) to do so. Thus, when you generate your login form with the button, it will need to have that (random) state token in it.

&nbsp;

Let’s say we have the following, either from registering with our provider, or generated:

<ul>
<li>Assigned by provider:
<ul>
<li>Client ID</li>
<li>Client Secret</li>
</ul>
</li>
<li>Chosen by you:
<ul>
<li>Application Name</li>
<li>State (a CSRF token)</li>
<li>Redirect URI (pick a name like <strong>appspot.com/oidcauth</strong>)<a href="#_ftn1" name="_ftnref1"><sup>[1]</sup></a></li>
<li>Nonce (random integer)</li>
</ul>
</li>
</ul>
&nbsp;

Let’s assume you have the following values for the sake of discussion:

<ul>
<li>client_id=myClientID</li>
<li>client_secret=myClientSecret</li>
<li>state=abcd1234</li>
<li>nonce=1234</li>
<li>redirect_uri=https://yourserver.appspot.com/oidcauth</li>
</ul>
&nbsp;

You’ll create a login link that has everything in it but the client_secret:

<table>
<tbody>
<tr>
<td width="624">&lt;a href=”https://accounts.google.com/o/oauth2/v2/auth?response_type=code&amp;client_id=myClientID&amp;scope=openid%20email&amp;state=abcd1234&amp;nonce=1234&amp;redirect_uri=https%3A//yourserver.appspot.com/oidcauth”

&gt;Login with Google&lt;/a&gt;</td>
</tr>
</tbody>
</table>
There are numerous ways you can get that link into your login form. You can use a template system like Jinja, or you can use reqJSON from previous labs to get all of this data and create a request. You can even use a form with method “GET”, and set all of the parameters in hidden fields, only exposing the “submit” button.

&nbsp;

Note that this example is using Google’s OpenID Connect service. In real life, you might use another service, and they will have what’s called a “<a href="https://developers.google.com/identity/protocols/OpenIDConnect#discovery">Discovery Document</a>” that you can use to get the host and path of the URL for your link. In this case it was “<a href="https://accounts.google.com/o/oauth2/v2/auth">https://accounts.google.com/o/oauth2/v2/auth</a>”, but you might use something different.

&nbsp;

That <strong><em>scheme://host/path</em></strong> part was obtained from Google’s discovery document, located here under the key “authorization_endpoint”: <a href="https://accounts.google.com/.well-known/openid-configuration">https://accounts.google.com/.well-known/openid-configuration</a>

&nbsp;

So, what is that link all about, and how does the information flow around? Check out the following graphic, and see if it makes any sense to you:

This is the OIDC 3-legged auth flow. It goes something like this:

<ul>
<li>Go to your site’s /login page
<ul>
<li>Request /login</li>
<li>Get back a login form with the link above inside of it. That link contains a bunch of information. Constant Client ID and redirect_uri, and random state and nonce.</li>
</ul>
</li>
<li>Click the “login with google” link (or similar)
<ul>
<li>Request login page from Google (or other provider)</li>
<li>Get back a login form or something where you can affirmatively say “yes, use this account to authenticate”.</li>
</ul>
</li>
<li>Submit responses, get logged in.
<ul>
<li>Responses get submitted to e.g., Google, which does the heavy lifting of authenticating.</li>
<li>Google responds with a redirect that your browser intercepts and acts on immediately. That redirect goes <em>to your site, the URI you specified</em>.</li>
<li>The browser sends a request <strong>to your site</strong> with the information from Google.
<ul>
<li>Your site checks that the state matches what is expected, then
<ul>
<li>Sends a request to Google with the code it got, asking for an actual access token. Only here is the client secret used.</li>
<li>Google responds with the JWT (identity), access token, and nonce, which your site can check to ensure that it’s the expected nonce.</li>
</ul>
</li>
<li>Your site creates and stores a session token for the user in the JWT.</li>
</ul>
</li>
<li>Your site responds with a cookie containing the session token. Typically it will do this in a 302 redirect response that causes you to go to the main page of your site (because now you are logged in!)</li>
</ul>
</li>
</ul>
<h2>CSRF Protection Required</h2>
There are two kinds of protections that OpenID Connect requires us to implement, both related to CSRF, but not quite the same. The first is called the “state”, which is a plain old CSRF token. The second is the “nonce”, and it acts in much the same way, but for a different stage of the process, ensuring that front and back channel communication are part of the same login.

&nbsp;

I used <strong>str(uuid.uuid4())</strong> to generate both of mine, then I used the double-cookie-submit approach, where I sent them down in cookies <em>and</em> as form values. The former is done using “set_cookie”, and the latter is done either by template injection or JavaScript creating the link from cookie values. You can choose whichever you like. Yes, templatizing your form page is allowed for this purpose.

&nbsp;

When your redirect_uri is hit, you will check that the cookies match the values in the request, and that will help you be sure that you are really talking to the right person.

<h2>Redirect URI</h2>
Your redirect_uri is an endpoint on <em>your server</em> that the <em>browser</em> will contact after the user has logged in to whatever ID provider you are sending them to. I’m calling mine “/oidcauth” inside of my Python file. When I send it to the ID provider, it will need to be a complete URL, including host, etc. That means I’ll need to know <em>where I’m deployed</em> before I attempt to log someone in.

&nbsp;

If you are on “yourserver.appspot.com”, that means the redirect_uri needs to include that hostname, which is how we’ve been doing it above.

&nbsp;

What does the handler (in Python) for the redirect_uri do? It is basically a combination of registration and login all in one, but with a twist. Here are the steps it takes:

<ul>
<li>Get code from request.args[‘code’]</li>
<li>Get state from request.args[‘state’]</li>
<li>Get nonce from your cookies (you should have set it in in a cookie when sending back the login form)</li>
<li>Verify that “state” is what it should be (I’m comparing it to a cookie called “oidc_state”, which I set when sending down the login form)</li>
<li>Get the client secret from the datastore</li>
<li>Create a URL that contains parameters for
<ul>
<li>code</li>
<li>client_id</li>
<li>client_secret</li>
<li>redirect_uri</li>
<li>grant_type = “authorization_code”</li>
</ul>
</li>
<li>Send a POST request to the ID provider’s token endpoint (for Google that’s “<a href="https://oauth2.googleapis.com/token">https://oauth2.googleapis.com/token</a>”, but check the <a href="https://accounts.google.com/.well-known/openid-configuration">Discovery Document</a> to be sure, as it may change, and that’s why discovery documents exist). You can do this with the Python <em>requests</em> library, like this: <strong><em>post(url, data)</em></strong>, where the data is a dictionary of all of the parameters you are supposed to send on the back channel to Google.</li>
<li>Get a response back that contains an “id_token”, which is a JWT that will contain the user’s name and other information.</li>
<li>Check that the nonce matches the one from the cookie.</li>
<li>If that user doesn’t exist in the database, create it.</li>
<li>Create a session token as normal, with this new username, set a cookie, and redirect.</li>
</ul>
&nbsp;

And then you’re done!

&nbsp;

It’s a lot less than it appears to be. But there are indeed some moving parts.

&nbsp;

To reiterate, you can send a POST request using the requests library (if you are using Flask, this comes down with it as a dependency):

<table>
<tbody>
<tr>
<td width="624">import requests

response = requests.post(“https://oath2.googleapis.com/token”,

{“code”: code,

“client_id”: your_client_id,

“client_secret”: your_client_secret_from_the_datastore,

“redirect_uri”: your_redirect_uri,

“grant_type”: “authorization_code”})
</td>
</tr>
</tbody>
</table>
<h2>JWT Unpacking</h2>
I don’t know of any libraries <em>in particular</em> that you should use for unpacking the JWT, but you should know that traditional Base64 padding is <strong>not</strong> included in the JWT body. That means you need to add an appropriate number of padding bytes (=) before it will work, depending on its length. Here’s my code that unpacks the JWT (called “id_token” here) to get the user information:

<table>
<tbody>
<tr>
<td width="624">_, body, _ = id_token.split(‘.’)

body += ‘=’ * (-len(body) % 4)

claims = json.loads(base64.urlsafe_b64decode(body.encode(‘utf-8’)))</td>
</tr>
</tbody>
</table>
&nbsp;

That should give you a Python dictionary that contains things like “sub” and “email” keys.

&nbsp;

At that point, you can create a user. I personally use the “sub” as the user’s <strong>key</strong>, and “email” is stashed away in there in case I need it later. Note that even though you don’t use the user’s password hash anymore, you <strong>still need the user object</strong> because it will be a parent of all of the events stored for that user.

<h1>Creating a Session</h1>
Once you have the claims as described above, you can get the user’s unique identifier from the “sub” field. I check that the user doesn’t exist, and if they don’t, I create them. Then I create a session that refers to that user’s sub (their “username” is the sub – a real username isn’t meaningful in this context, since you never need to interact with that directly – you just click the “Login with Google” button instead), create a cookie, and redirect to the home page. The user has now logged in using OpenID Connect!
