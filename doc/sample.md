Account sign up
------------

Contact info@qindom.com to get 

qit_access_user_name; qit_access_secrect_key; aws_access_key_id; aws_secret_access_key

Saple code
------------

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
