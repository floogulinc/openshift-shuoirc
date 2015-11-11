Shuo on OpenShift
=========================

Shuo is a free, open, always connected web IRC client.

Running Shuo on OpenShift
--------------------

The easiest way to deploy Shuo on OpenShift is with the [Client Tools](https://developers.openshift.com/en/managing-client-tools.html).

Start by creating a Node.js application:

    rhc app create <appname> nodejs-0.10 --from-code=https://github.com/floogulinc/openshift-shuoirc.git

Connect to your application remotely using SSH:

    rhc ssh <appname>

This setup assumes you want to run Shuo in its private mode. You will need to create your Shuo login:
    
    cd $OPENSHIFT_REPO_DIR
    ./shuo add <username>

Additionally, remove the default user (optional):

    ./shuo remove default