Gradle script to setup portable Git to use SSH
=========================

When using Git, SSH is the best way to authenticate with server. If HTTPS is used, you need to type the password every time. But SSH is not that easy to setup. You can find a lot of online articles about how to set this up correctly. You need to generate correct SSH keys and add your public key to GitHub or Bitbucket using their web pages. You also need to keep ssh-agent running to avoid typing passphrase every time.

This script tries to solve this problem by setting up Git quickly. This script can 
* Download portable Git binaries and configure it
* Create SSH keys and install keys to remote server

## How to use ##

This script is written using Gradle, so you need to download and configure Gradle correctly. You can find [instructions](http://gradle.org/docs/current/userguide/installation.html) on Gradle's website.

You also need to install [7-zip](http://www.7-zip.org/) to unzip package of portable Git bundle. 7-zip is assumed to be installed in the default <code>C:\Program Files\7-Zip</code> folder. If you changed that, running Gradle using <code>-P7zipDir={7ZIP_DIR}</code> to override it.

Then you need to change settings in <code>user.conf</code> file to include your name and email.

    git_name = You name
    git_email = youremail@example.org

After that, you can run this script to download portable Git binaries and configure it with GitHub or Bitbucket.
* For GitHub, run <code>gradle installSSHKey_github</code>.
* For Bitbucket, run <code>gradle installSSHKey_bitbucket</code>.

After the script runs successfully, you can a <code>git</code> folder in your current directory, use <code>git-bash.bat</code> or <code>git-cmd.bat</code> to start Git. When the first time you are using Git, you need to input the passphrase, the value is <code>gituser</code>.