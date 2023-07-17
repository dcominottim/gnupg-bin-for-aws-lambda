# GNUPG binaries compiled for AWS Lambda

Ever since Python 3.8, GNUPG binaries stopped being included in AWS-managed lambda layers and runtimes. Therefore, if we want to use GNUPG inside of lambda functions using Python >= 3.8, it is necessary to 

1. Manually compile the binaries in an appropriate way to target the desired AWS lambda runtime
2. Create a custom lambda layer (putting all the GNUPG binaries inside of a `bin` folder, which should be compressed into a ZIP file and used as a source/package for the layer)
3. Attach the custom lambda layer to our AWS lambda function

After doing that, the GNUPG binaries will be available in `/opt/bin`.

I have performed such compilation based on this StackOverflow post that has a great step-by-step on how to do it using Docker: https://stackoverflow.com/a/74550493/5078914.
