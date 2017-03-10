# Design

This section is meant to explain and defend the design of `guillotina`.



## JavaScript application development focus


One of the main driving factors behind the development of `guillotina` is to
streamline the development of custom web applications.

Some of the technologies we support in order to be a great web application development
platform are:

- Everything is an API endpoint
- JWT
- Web sockets
- Configuration is done with JSON
- URL to object-tree data model

## Speed

A primary focus of `guillotina` is speed. We take shortcuts and may use some
ugly or less-well conceptually architected solutions in some areas in order
to gain speed improvements.

Some of the decisions we made affect how applications and addons are designed.
Mainly, we try to stay light on the amount of data we're loading from the
database where possible and we try to lower the number of lookups we do in
certain scenarios.

That being said, `guillotina` is not a barebones framework. It provides a lot
of functionality so it will never be as fast as say Pyramid.

"There are no solutions. There are only trade-offs." - Thomas Sowell


## Asynchronous

`guillotina` is asynchronous from the group up, built on top of `aiohttp`
using Python 3.6's asyncio features.

Practically speaking, being built completely on asyncio compatible technologies,
`guillotina` does not block for network IO to the database, index catalog,
redis, etc or whenever you'd integrated.

Additionally, we have support for async utilities that run in the same async
loop and async content events.

Finally, the web server can also support web sockets OOTB.


## Tooling

I've talked some about it but these are the basic technologies `guillotina`
is built with:

- aiohttp


## Security

`Guillotina` uses the same great security infrastructure that Plone
has been using for the last 15 years.


## Style

Stylistically, currently the project isn't extremely coherent right now so I'll speak
to what we'd like to work toward stylistically long term::

- JSON configuration
- Pyramid-like idioms and syntax where it makes sense
- Functions + decorators over classes