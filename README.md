A simple Play 2.1 application showing how to stream an HTTP file upload
=======================================================================

The Play 2.1 Iteratee examples for doing file upload do not explain how to use small in-memory buffers to stream an
upload from the client to a destination. Large uploads, such as movies, should not be completely buffered by the Play
app before copying the data to the destination. This small demo shows how large files can be copied from client to a
destination without requiring any temporary files, and requiring a minimal memory footprint. For example, FireFox sends
8KB chunks when uploading files, so only a few chunks would be held in memory for each client performing a transfer.

This demo streams a File upload to a local file; you could easily modify this example to stream elsewhere, such as
AWS S3 using the [AWS Java SDK](http://aws.amazon.com/documentation/sdkforjava/).

Just clone the repo and run it with Play on your local machine:
<pre>play debug run</pre>

You'll find inline comments in the code.
