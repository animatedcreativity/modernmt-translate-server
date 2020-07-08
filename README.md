# modernmt-translate-server

Server for text translations using ModernMT. Translations are stored in a database for future usage to save costs.  
See also: https://www.npmjs.com/package/modernmt-translate

Can translate full HTML documents.

Made for personal use only.  
For commercial use, please contact ModernMT itself.  

### Configuration
```
exports = module.exports = function() {
  return {
    authorization: "<your_server_authorization_key>", // Lowercase
    expressHost: "127.0.0.1",
    expressPort: 3000,
    database: "database/translations",
    endpoint: "/translate",
    key: "", // Get an API key here: https://www.modernmt.com/pricing/
    cdn: { // dbpouch CDN, if needed.
      use: false,
      email: "<email>",
      apiKey: "<api_key>",
      domain: "<domain>",
      folder: "<folder>"
    }
  }
};
```

Add a file named `modernmt-translate-server.js` in parent folder or in the project itself with above configuration.

### API Requests

Translate
```
curl \
  -d '{"text": "This is a test line.", "from": "eng", "to": "swe"}' \
  -H "content-type: application/json" \
  -H "authorization: <your_server_authorization_key>" \
  https://<your_server_name>/translate; echo
```

Languages
```
curl \
  -H "authorization: <your_server_authorization_key>" \
  https://<your_server_name>/languages; echo
```

OR, use `modernmt-translate` module to make API requests: https://www.npmjs.com/package/modernmt-translate

Happy coding!