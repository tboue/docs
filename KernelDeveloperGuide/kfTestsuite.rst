Setup a KF Test Suite
=====================

A KF test suite can be executed when building a Foundation Library or an Add-On library, 
and usually extends the tests written for the :ref:`default library test suite <application_testsuite>` to verify the behavior
of this library when its APIs are exposed by a Kernel.

A KF test suite is composed of a set of KF tests, each KF test itself is a minimal MicroEJ Multi-Sandbox Firmware composed of a Kernel and zero or more Features.


Enable the Test Suite
---------------------

In an existing library project:

- Create the ``src/test/projects`` directory,
- Edit the ``module.ivy`` and insert the following line within the ``<ea:build>`` XML element:

::

    <ea:plugin organisation="com.is2t.easyant.plugins" module="microej-kf-testsuite" revision="+" />


Add a KF Test
-------------

A KF test is a structured directory placed in the ``src/test/projects`` directory.

- Create a new directory for the KF test
- Within this directory, create the sub-projects:
  
  - Create a new :ref:`module project <mmm_module_skeleton>` for the Kernel using the ``microej-javalib`` skeleton,
  - Create a new :ref:`module project <mmm_module_skeleton>` for the Feature using the ``application`` skeleton,
  - Create a new :ref:`module project <mmm_module_skeleton>` for the Firmware using the ``firmware-multiapp`` skeleton.


The names of the project directories are free, however MicroEJ suggests the following naming convention, assuming the KF test directory is ``[TestName]``:

- ``[TestName]-kernel`` for the Kernel project, 
- ``[TestName]-app[1..N]`` for Feature projects,
- ``[TestName]-firmware`` for the Firmware project. 

The KF Test Suite structure shall be similar to the following figure:

.. figure:: png/kf_testsuite_project_structure.png
   :alt: KF Test Suite Structure
   :align: center

   KF Test Suite Overall Structure

All the projects will be built automatically in the right order based on their dependencies.

KF Test Suite Options
---------------------
   
It is possible to configure the same options defined by :ref:`Test Suite Options <testsuite_options>` for the KF test suite, 
by using the prefix ``microej.kf.testsuite.properties`` instead of ``microej.testsuite.properties``.

..
   | Copyright 2020-2021, MicroEJ Corp. Content in this space is free 
   for read and redistribute. Except if otherwise stated, modification 
   is subject to MicroEJ Corp prior approval.
   | MicroEJ is a trademark of MicroEJ Corp. All other trademarks and 
   copyrights are the property of their respective owners.
