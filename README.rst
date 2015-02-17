Asyncio fork of ovh's lightweight wrapper around OVH's APIs.

.. code:: python

    # -*- encoding: utf-8 -*-

    import ovh
    import asyncio

    def main():
        # Instantiate. Visit https://api.ovh.com/createToken/index.cgi?GET=/me
        # to get your credentials
        client = ovh.Client(
            endpoint='ovh-eu',
            application_key='<application key>',
            application_secret='<application secret>',
            consumer_key='<consumer key>',
        )

        # Print nice welcome message
        print("Welcome", (yield from client.get('/me')['firstname']))

    if __name__ == '__main__':
        loop = asyncio.get_event_loop()
        loop.run_until_complete(main())
 