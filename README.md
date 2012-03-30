# pgpool-II for dotCloud

If the connection time to your PostgreSQL database is killing the performance of your application, don't despair: try this connection pooler instead!

## What?

This recipe will install the pgpool-II connection pooler inside any dotCloud service.

Note: for now, it was tested only with Python, so YMMV.

## How?

1. Edit your ``dotcloud.yml`` file to add a ``processes:`` section to the service which needs the connection pooler, as shown in the sample ``dotcloud.yml`` file in the recipe.
2. Copy the ``run.pgpool2`` script to the approot of this service.
3. Change your connection parameters; instead of connecting to the dotCloud-supplied host and port, use ``localhost`` and ``5433``. Don't change login/password/db information.
4. Push and enjoy!

## Caveats?

The connection pooler will autoconfigure itself using the first PostgreSQL service it will find. If you have multiple PostgreSQL services in your stack, it will probably NOT do what you want. In that case, just edit ``run.pgpool2`` and change the first lines to grep for the correct variables in your environment.
