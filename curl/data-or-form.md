# Data or Form

## `--data`

Issues a `POST` request automatically as `Content-Type: application/x-www-form-urlencoded`. The same as submitting an HTML form in a browser.

```
Example:

    curl -d name=John https://example.com/

Example: send form data from a local file

    curl -d @filename https://example.com
```

## `--form`

`content-type: multipart/form-data`

Issues a `POST` request with `Content-Type: multipart/form-data`. This enables uploading of binary files etc.

```
Example:  send an image to an HTTP server, where 'profile' is the name of the form-field to which the file portrait.jpg will be the input:

    curl -F profile=@portrait.jpg https://example.com/upload.cgi

Example: send a your name and shoe size in two text fields to the server:

    curl -F name=John -F shoesize=11 https://example.com/

Example: send a your essay in a text field to the server. Send it as a plain text field, but get the contents for it from a local file:

    curl -F "story=<hugefile.txt" https://example.com/
```

## Resources

[man curl](https://manpages.org/curl)
