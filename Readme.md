Java Development Kit (JDK) installation script for Linux
========================================================

"install-java.sh" is an installation script for setting up Java Development Kit (JDK) on Debian based Linux Operating Systems.

Currently, the `install-java.sh` script supports `tar.gz` distributions from [Oracle](https://www.oracle.com/technetwork/java/index.html), [OpenJDK](http://openjdk.java.net/) and [AdoptOpenJDK](https://adoptopenjdk.net/)

I'm mainly using Ubuntu and therefore this script is tested only on different versions of Ubuntu.

## Prerequisites

The script uses "unzip" command. Therefore, please make sure it is installed.

`sudo apt install unzip`

The "install-java.sh" script will not download the Java distribution. You must download JDK `tar.gz` distribution.

For Oracle JDK 7 & 8, `install-java.sh` supports installing demos and "Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy Files". This files are picked up from the same directory.

For example, if you want to install Java 7, then the following files should be downloaded and moved to a single directory.

 - jdk-7u80-linux-x64.tar.gz
 - jdk-7u80-linux-x64-demos.tar.gz
 - UnlimitedJCEPolicyJDK7.zip

Similarly for Java 8, following are the files required

 - jdk-8u212-linux-x64.tar.gz
 - jdk-8u212-linux-x64-demos.tar.gz
 - jce_policy-8.zip

The Java Demos and Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy files are optional. There are no demos from Java 9 upwards. Since Java 9, default JCE policy files already allow for "unlimited" cryptographic strengths.

For any other JDK, you only need to have the Java binary distribution.

## Installation

The script needs to be run as root.

You need to provide the JDK distribution file (`tar.gz`) and the Java Installation Directory. The default value for Java installation directory is "/usr/lib/jvm"

```console
$ sudo ./install-java.sh -h

Usage: 
install-java.sh -f <java_dist> [-p <java_dir>]

-f: The jdk tar.gz file.
-p: Java installation directory. Default: /usr/lib/jvm.
-h: Display this help and exit.

```
