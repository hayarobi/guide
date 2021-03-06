Name System
===========

Aergo contains a name service to translate addresses into easy to remember short names.

One name maps to exactly one address. Names are currently fixed to a length of 12 characters.

Using the name system
---------------------

The easiest way to create and update names is the `aergocli <../tools/aergocli.html>`_. 

Registering and updating names currently requires spending 1 aergo.

To register a new name:

.. code-block:: text

    aergocli name new --from my_unlocked_account_address --name my12charname

To retrieve the owner of a registered name:

.. code-block:: text

   aergocli name owner --name my12charname
   
To change mapping the name:

.. code-block:: text

    aergocli name update --from my_unlocked_account_address --to account_address --name my12charname


Technical details
-----------------

Names are stored in the state of the special account :code:`aergo.name`. They are created and updated using special governance transactions.
Refer to `transaction types <transaction-types.html>`_ for the technical specification of these actions.
Governance transactions currently don't require any fee, but the name system requires an amount of 1 aergo to be included in the transaction.

Transactions that create or update names are effective after they are included in a block.
That means that you can only refer to new or updated names in the following block.

