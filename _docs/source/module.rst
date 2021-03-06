As a Module
===========

There are two ways to give in the Azure KeyVault credentials, either set environment variables for:

.. code-block::

    AZURE_VAULT_BASE_URL=***
    AZURE_CLIENT_ID=***
    AZURE_SECRET_KEY=***
    AZURE_TENANT_ID=***

or set them while calling the object.

Get a Single Secret
-------------------

You can get a single secret with the following example:

.. code-block:: python

    from azsecrets import AzureSecrets

    secrets = AzureSecrets('https://', 'client id', 'secret key', 'tenant id')
    print(secrets.get_secret('secret-name'))
    # secret-value

Get All Secrets
---------------

.. code-block:: python

    from azsecrets import AzureSecrets

    secrets = AzureSecrets('https://', 'client id', 'secret key', 'tenant id')
    print(secrets.get_secret())
    # {
    #     'secret-name-1' : 'secret-value-1',
    #     'secret-name-2': 'secret-value-2'
    #      ...
    # }

Get Specific Set of Secretes
----------------------------

You can also get a specific set of secrets present in your Azure KeyVault by doing:

.. code-block:: python

    from azsecrets import AzureSecrets

    secrets = AzureSecrets('https://', 'client id', 'secret key', 'tenant id')
    print(secrets.get_secret(['secret-name-1', 'secret-name-2']))
    # {
    #     'secret-name-1' : 'secret-value-1',
    #     'secret-name-2': 'secret-value-2'
    # }

Package Contents
----------------

.. autoclass:: azsecrets.AzureSecrets
    :members:
    :private-members: