Deployment
==========

Overview
--------

For some projects, a complete integration workflow includes automated deployment right after a successful build, drone can do this.

Drone provides automated deployment system which may be configured from within .drone.yml file, and you just have to specify `deploy` option
with any plugins available. Available plugins and their options listed below.

One thing to note, since most of the deployment plugins use ssh, you may want to make sure that the target systems already authorize drone's public key.
You can see your repository public key at repository settings page, within `Key Pairs` tab.


heroku
------

.. code-block:: yaml

    deploy:
      heroku:
        app: lightningfoobar
        force: false
        branch: live

Above is an example of a deployment to heroku PaaS with an app named `lightningfoobar`, and will be triggered only when
drone get commits at a branch named `live`.

