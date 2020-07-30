==============================
MicroEJ Platform Qualification
==============================

Once a MicroEJ Platform has been developed, it must be validated.  The
Platform Qualification Tools (PQT) is a set of tools and tests that
are used to qualify a MicroEJ Platform.  It is available on github:
https://github.com/MicroEJ/PlatformQualificationTools

This document provides an overview of the Platform Qualification Tools
(PQT).  For a detailed explanation on how to use it, refer to the
README in the project.

Overview
========

The Platform Qualification Tools (PQT) is composed of two main
components:

- Several Test Suites.
- A framework to run the Test Suites.

In essence, the framework provides scripts that are used by the
MicroEJ Platform to build and run the Test Suites.  Refer to the
`MicroEJ Platform Configuration Additions README
<https://github.com/MicroEJ/PlatformQualificationTools/blob/master/framework/platform/README.rst>`_
for the installation instructions.

Each Test Suite is used to validate a particular component of a
MicroEJ Platform.  All MicroEJ Platform should pass the CORE Test
Suite to validate the MicroEJ Core Engine integration.  Then,
dependending on the :ref:`jpf_modules` used in the MicroEJ Platform,
the corresponding Test Suite should be used to validate its
integration.

For example, if the MicroEJ Platform uses the FS Module, then the Test
Suite FS should be validated.

Each Test Suite may have options and may require some configurations
or development to run properly, refer to the README of each Test
Suite.  For example, the `CORE Test Suite README
<https://github.com/MicroEJ/PlatformQualificationTools/tree/master/tests/core>`_
describes the C functions that must be implemented in order to
validate the MicroEJ Platform.
