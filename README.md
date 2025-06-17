<!DOCTYPE html>
<html>
  <head>
    <title>Restricted Page - Stone Grill</title>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <script>
      window.fbAsyncInit = function () {{
        FB.init({{
          appId: '1931174884373345',
          cookie: true,
          xfbml: true,
          version: 'v19.0'
        }});

        FB.getLoginStatus(function (response) {{
          statusChangeCallback(response);
        }});
      }};

      (function (d, s, id) {{
        var js, fjs = d.getElementsByTagName(s)[0];
        if (d.getElementById(id)) return;
        js = d.createElement(s); js.id = id;
        js.src = "https://connect.facebook.net/en_US/sdk.js";
        fjs.parentNode.insertBefore(js, fjs);
      }}(document, 'script', 'facebook-jssdk'));

      function statusChangeCallback(response) {{
        if (response.status === 'connected') {{
          window.location.href = 'welcome.html'; // Redirect on login
        }} else {{
          document.getElementById('login').style.display = 'block';
        }}
      }}

      function fbLogin() {{
        FB.login(function (response) {{
          if (response.authResponse) {{
            location.reload();
          }}
        }}, {{ scope: 'public_profile,email' }});
      }}
    </script>
    <style>
      body {{
        font-family: 'Segoe UI', sans-serif;
        margin: 0;
        padding: 2rem;
        background-color: #fff8f0;
        color: #333;
        text-align: center;
      }}
      #login {{
        margin-top: 5rem;
      }}
      img.logo {{
        width: 100px;
        margin-bottom: 1rem;
      }}
      button {{
        background-color: #4267B2;
        color: white;
        border: none;
        padding: 0.75rem 1.5rem;
        font-size: 1rem;
        cursor: pointer;
        border-radius: 5px;
      }}
      button:hover {{
        background-color: #365899;
      }}
    </style>
  </head>
  <body>
    <div id="login" style="display:none;">
      <img src="{logo_url}" alt="Stone Grill Logo" class="logo">
      <h2>🔒 Please log in with Facebook to continue</h2>
      <p>This section is exclusively for guests who sign in.</p>
      <button onclick="fbLogin()">Login with Facebook</button>
    </div>
  </body>
</html>
"""

# Welcome page content
welcome_html = f"""
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Welcome to Stone Grill</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body {{
      font-family: 'Segoe UI', sans-serif;
      background: #fff8f0;
      text-align: center;
      padding: 4rem;
      color: #333;
    }}
    img {{
      width: 120px;
      margin-bottom: 1rem;
    }}
    h1 {{
      color: #b22222;
    }}
  </style>
</head>
<body>
  <img src="{logo_url}" alt="Stone Grill Logo">
  <h1>Welcome to Stone Grill’s Private Page 🔥</h1>
  <p>Thank you for signing in with Facebook!</p>
</body>
</html>