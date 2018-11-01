.. image:: https://github.com/quantumlib/cirq/blob/master/docs/Cirq_logo_color.svg
  :alt: QIT
  :width: 500px

Qit is a quantum ready machine learning platform.

The qindomClient SDK is an open source tool built on top of python that provides API connections to QIT services. With minimal configuration, you can start using all of the machine learning algorithms that natively designed and implemented by the Qindom team. QIT is designed to serve Quantum Machine Learning methods and algorithm to public, and we are dedicated to build a whole new ML/AL eco-system.

.. image:: https://travis-ci.com/quantumlib/Cirq.svg?token=7FwHBHqoxBzvgH51kThw&branch=master
  :target: https://travis-ci.com/quantumlib/Cirq
  :alt: Build Status

.. image:: https://badge.fury.io/py/cirq.svg
    :target: https://badge.fury.io/py/cirq

Installation
------------

Follow these
`instructions <https://github.com/Qindom/QIT/blob/master/doc/install.md>`__.

Hello Qubit
-----------

A simple example to get you up and running:

.. code-block:: python

  import cirq

  # Pick a qubit.
  qubit = cirq.GridQubit(0, 0)

  # Create a circuit
  circuit = cirq.Circuit.from_ops(
      cirq.X(qubit)**0.5,  # Square root of NOT.
      cirq.measure(qubit, key='m')  # Measurement.
  )
  print("Circuit:")
  print(circuit)

  # Simulate the circuit several times.
  simulator = cirq.google.XmonSimulator()
  result = simulator.run(circuit, repetitions=20)
  print("Results:")
  print(result)

Example output:

.. code-block:: bash

  Circuit:
  (0, 0): ───X^0.5───M('m')───
  Results:
  m=11000111111011001000


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
