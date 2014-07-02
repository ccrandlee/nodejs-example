Node.js on OpenShift
====================

This git repository helps you get up and running quickly w/ a node.js installation
on OpenShift. Previous contents of this repository was obsoleted, as currently
the basic application created using OpenShift CLI matches exactly its previous
contents.

Running nodejs app on OpenShift
-------------------------------

Create an account at https://www.openshift.com

Install git, rubygems and rhc client for interacting with openshift infrastructure.
Detailed instructions per OS are available at https://www.openshift.com/developers/rhc-client-tools-install.

Create a nodejs-0.10 application using rhc:

    rhc app create <appname> nodejs-0.10

That's it, you can now checkout your application at:

    http://<appname>-<yournamespace>.rhcloud.com

Now you can modify the code, commit and push back up to your OpenShift application using:

    git commit
    git push

For that it might be useful to know a little about git workflow, sample tutorial
can be found [here](http://git-scm.com/docs/gittutorial).

Finally full OpenShift `nodejs` cartridge documentation can be found at:
http://openshift.github.io/documentation/oo_cartridge_guide.html#nodejs


Repo Layout
-----------

    .openshift/                 - Location for OpenShift specific files.
    .openshift/action_hooks/    - Entry points into various application and
                                  platform lifecycle operations.
    .openshift/cron/            - Scripts or jobs to be run on a periodic basis.
    .openshift/markers/         - Marker files, eg. hot_deploy enabling hot
                                  deploy feature.
    node_modules/               - Any node modules packaged with the app.
    README.md                   - This file.
    deplist.txt                 - Deprecated.
    index.html                  - Default OpenShift page seen when you open your
                                  app in a web browser.
    package.json                - npm package descriptor.
    server.js                   - Main application file, where the whole logic
                                  is placed.
