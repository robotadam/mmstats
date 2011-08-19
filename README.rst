====
Wat?
====

Mmstats is a way to expose and read (slurpstats.py) diagnostic/statistical
values for applications.

You could think of mmstats as /proc for your application and slurpstats.py as one
of the procps tools.

-----
Goals
-----

* Separate publishing/writing from consuming/reading tools
* Platform/language independent (a Java writer can be read by a Python tool)
* Predictable performance impact for writers via:

  * No locks (1 writer per thread)
  * No syscalls
  * All in userspace
  * Reading has no impact on writers

* Optional persistent (writer can sync anytime)
* 1-way (Publish/consume only; mmstats are not management extensions)

=====
Usage
=====

-------------------
Testing/Development
-------------------

#. Run your favorite Python test runner (py.test or nosetests)
#. Run slurpstats.py
#. Clean /tmp/mmstats-* files up
