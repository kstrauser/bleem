Bleem
=====

Highly concurrent programming language tuned for raw performance

What is it?
-----------

Bleem is a new, multiparadigm language under active development. It features:

* Unmatchable performance. Bleem optimizes functions down to unused opcodes on the target CPU, then uploads firmware patches to the CPU to implement them. Typical Bleem functions execute in a single instruction commit.
* Ubiquitous proprietary compression. Bleem's own fast compression algorithms mean that it can store vast amounts of data in the heap. This is used pervasively throughout the runtime for such things as holding state information for 1,000,000 concurrent connections in 5MB of RAM.

What would you use it for?
--------------------------

If you've been looking for a one-size-fits-all language for making all other throughput bottlenecks disappear in a puff of smoke, Bleem is your answer. It combines the best aspects of Go, Erlang, Clojure, and Node.js into a single, expressive language. If you're thinking of using one of those to solve your performance or scalability problems, we encourage you to consider whether Bleem would fit your needs.

We've used Bleem to write a RESTful API server where a single medium-sized cloud server can handle many hundreds of thousands of concurrent requests.

What is Bleem *not* good for?
-----------------------------

Unfortunately, most databases, networks, SOA endpoints, etc. are not implemented in Bleem. Although our in-house NoSQL database ("NIH") has O(1) complexity with a 1-CPU-cycle constant for all operations, your data stores probably do not.

These problems can't be solved by a language with perfect performance characteristics:

* Database lookups for each web request
* Lack of a caching architecture
* Synchronous request handling
* Single-point-of-failure locking servers
* Dependence on clock synchronization
* Anything that the CAP theorem won't allow
* Dependence on a network that doesn't drop packets
* A system architecture where shaving a few milliseconds of the first processing stage won't make a 2-second backend delay in the rest of the system go away (aka "Amdahl's Law")

Bleem can give you a nearly infinitely-scalable frontend. If you have a perfect, scalable backend behind a slow interface, Bleem can make your problems disappear as if by magic. If your architecture is slow, though, fix that first: no new trendy language can handwave that away.

Availability
------------

We're cleaning Bleem up for public release. It should be available Real Soon Now.
