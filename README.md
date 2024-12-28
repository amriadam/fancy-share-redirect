<!DOCTYPE html>
<html>
<head>
  <title>Redirect</title>
  <script>
    // Extract the token from the URL and forward it to the extension
    const params = new URLSearchParams(window.location.hash.substring(1));
    const accessToken = params.get('access_token');
    if (accessToken) {
      const redirectUri = `chrome-extension://bmenakpomhdgfpmpekfokaagbbeond/redirect.html#access_token=${accessToken}`;
      window.location.href = redirectUri;
    } else {
      document.body.innerHTML = "Error: Unable to retrieve access token.";
    }
  </script>
</head>
<body>
  Redirecting...
</body>
</html>
