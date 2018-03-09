## upload a file to a server on the command line using curl  

What is Droopy?

Droopy is a mini Web server whose sole purpose is to let others upload files to your computer.
https://github.com/stackp/Droopy http://stackp.online.fr/?p=28

HTTP Server Upload Basics

The basic idea of file uploads is actually quite simple. It basically works like this: A

tag is marked with enctype=multipart/form-data and an is placed in that form.
http://flask.pocoo.org/docs/patterns/fileuploads/

What does droopy.py serve in the form element?

<form method="post" enctype="multipart/form-data" action="">
  <input name="upfile" type="file" multiple="yes">
  <input value="Send" onclick="swap()" type="submit">
</form>
Curl Man Page

-F, --form <name=content>
      (HTTP)  This  lets curl emulate a filled-in form in which a user
      has pressed the submit button.
What is the curl command to upload to droopy servers?

curl -i -F upfile=@hello.txt http://example.com/
What is the response to this curl command from the droopy server?

The -i flag to curl causes curl to emit this response on the command line:

HTTP/1.0 200 OK
Server: BaseHTTP/0.3 Python/2.7.3
Date: Sat, 07 Jun 2014 01:10:34 GMT
Content-type: text/html; charset=utf-8


<!doctype html>
<html>
<head><title> File received </title>
...
</html>
