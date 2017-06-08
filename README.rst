Running a Flask application over HTTPS with traefik and Let's Encrypt
=====================================================================

This is a dummy example to show how to run a flask_ application over HTTPS
using traefik_ and `Let’s Encrypt <https://letsencrypt.org>`_.

To obtain a real certificate from Let's Encrypt you need a valid domain
name. You have to forward port 80 and 443 to your machine IP if you
run this on a private network.

Note that you should put your real email in the `traefik/traefik.toml` file.

To test, run::

    # set the TRAEFIK_FRONTEND_RULE variable to "Host:<your domain>"
    $ export TRAEFIK_FRONTEND_RULE=Host:myhost.example.com
    $ docker-compose up

Go to https://myhost.example.com

Voilà!

For more information, see:
http://beenje.github.io/blog/posts/running-your-application-over-https-with-traefik

.. _flask: http://flask.pocoo.org
.. _traefik: https://traefik.io
