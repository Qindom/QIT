
QIT - a quantum ready machine learning platform
------------

The qindomClient SDK is an open source tool built on top of python that provides API connections to QIT services. With minimal configuration, you can start using all of the machine learning algorithms that natively designed and implemented by the Qindom team. QIT is designed to serve Quantum Machine Learning methods and algorithm to public, and we are dedicated to build a whole new ML/AL eco-system.

Installation
------------

Follow these instructions
https://github.com/Qindom/QIT/blob/master/doc/install.md

Account sign up
------------

Contact info@qindom.com to get 
qit_access_user_name;  qit_access_secrect_key;  aws_access_key_id;  aws_secret_access_key
--------------------------------------------------------------------------------------------------------------

install aws cli on your windows or linux
https://docs.aws.amazon.com/cli/latest/userguide/installing.html
--------------------------------------------------------------------------------------------------------------

in your windows command line interface or linux terminal run
<p>aws configure
<p>use aws_access_key_id  aws_secret_access_key to finish configuring

Sample code
-----------

A simple example to get you up and running
https://github.com/Qindom/QIT/blob/master/doc/sample.md

Documentation
-------------

See
`here <https://cirq.readthedocs.io/en/latest/>`__
or jump into the
`tutorial <https://cirq.readthedocs.io/en/latest/tutorial.html>`__.

Contributing
------------

We welcome contributions. Please follow these
`guidelines <https://github.com/quantumlib/cirq/blob/master/CONTRIBUTING.md>`__.

We use
`Github issues <https://github.com/quantumlib/Cirq/issues>`__
for tracking requests and bugs. Please post questions to the
`Quantum Computing Stack Exchange <https://quantumcomputing.stackexchange.com/>`__ with a 'cirq' tag.

See Also
--------

For those interested in using quantum computers to solve problems in
chemistry and materials science, we encourage exploring
`OpenFermion <https://github.com/quantumlib/openfermion>`__ and
its sister library for compiling quantum simulation algorithms in Cirq,
`OpenFermion-Cirq <https://github.com/quantumlib/openfermion-cirq>`__.

Disclaimers
----------
**Cirq is currently in alpha.** We are still making breaking changes, and we *will* break your code when we make new releases. We recommend that you pin a specific version of cirq in `requirements.txt` files, and periodically bump to the latest release. That way you have control over when a breaking change affects you.

Cirq is not an official Google product. Copyright 2018 The Cirq Developers
