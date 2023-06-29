# GNUPG binaries compiled for AWS Lambda

Ever since Python 3.8, GNUPG libraries stopped being included in AWS-managed lambda layers and runtimes. Therefore, it is necessary to manually compile the binaries in an appropriate way to target the AWS lambda runtime, and after that we must create a custom lambda layer (packing all the GNUPG binaries in ZIP format and using that as a source/package for the layer) and attach it to our AWS lambda function. The binaries will then be available in /opt/bin.

I have performed sich compilation based on this StackOverflow post that has a great step-by-step on how to do it using Docker: https://stackoverflow.com/a/74550493/5078914.
