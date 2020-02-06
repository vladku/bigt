.. Bigt documentation master file, created by
   sphinx-quickstart on Sat Jan 25 17:25:33 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Bigt's documentation!
================================

Extention of the inbuild dict type.
Main reason is add merge and issubset method to simplify working with nested dictionaries.

Examples:

.. code-block:: python
   :linenos:

    a = {"a": {"a": "str", "b": 123}}
    b = {"a": {"a": "str", "b": 1234}}
    result, not_present, changed = DictExt(b).issubset(a)
    assert not result
    assert changed == {"a": {"b": {"old": 1234, "new": 123} } }
    assert not not_present

.. code-block:: python
   :linenos:

    >>> DictExt({"a": 3, "b": [{"b": 123}]}) + DictExt({"a": 1, "c": False, "b": [{"a": 12.64}]})
    {'a': 1, 'b': [{'b': 123, 'a': 12.64}], 'c': False}

.. code-block:: python
   :linenos:

    >>> DictExt({"aa": 3, "a": [{"b": {"bv": 1, "bc": 2}, "a": 1}, [3,1,8,5]]}).sort()
    {'a': [[1, 3, 5, 8], {'a': 1, 'b': {'bc': 2, 'bv': 1}}], 'aa': 3}

.. toctree::
   :maxdepth: 2
   
   modules

Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`

