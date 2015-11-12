Shuo on OpenShift
=========================

Shuo is a free, open, always connected web IRC client.

Running Shuo on OpenShift
--------------------

The fastest way to deploy Shuo on OpenShift is by clicking [here](https://openshift.redhat.com/app/console/application_types/custom?cartridges[]=nodejs-0.10&initial_git_url=https://github.com/floogulinc/openshift-shuoirc.git&name=shuo).

Another way to deploy Shuo on OpenShift is with the [Client Tools](https://developers.openshift.com/en/managing-client-tools.html).

Start by creating a Node.js application:

    rhc app create <appname> nodejs-0.10 --from-code=https://github.com/floogulinc/openshift-shuoirc.git

Connect to your application remotely using SSH:

    rhc ssh <appname>

This setup starts with Shuo in public mode. You can change it to private in the `config.js` file and then you will need to create your Shuo login:
    
    cd $OPENSHIFT_REPO_DIR
    ./shuo add <username>

Additionally, remove the default user (optional):

    ./shuo remove default
