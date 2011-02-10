py-moneyed: provides data abstractions for money and currency
============================================================

The need to represent instances of money frequently arises in software
development, particularly any financial/economics software.  The
py-moneyed package provides the classes of Money and Currency to help
with that need, at a level more useful than just Python's Decimal
class, or ($DEITY forbid) float primitive.  The package is meant to be
stand-alone and easy to use directly, or subclass further.

Some of the py-moneyed code was first derived from python-money
available via this URL: http://code.google.com/p/python-money/ Because
the Google Code version has been inactive since May 2008, I forked it
and modified it for my needs in 2010. Compared to python-money, major
changes in py-moneyed include separating it from django usage,
tightening types handling in operators, a complete suite of unit
tests, PEP8 adherence, and providing a setup.py.


Usage
-----

On to the code: the Money class is instantiated with:

- An amount which can be of type string, float, or Decimal.
- A currency, which usually is specified by the  three-capital-letters
  ISO currency code,e.g. USD.

For example,

    x = Money(amount='99.99', currency='USD')

The Money class also provides operators with type checks, matching
currency checks, and sensible dimensional behavior, e.g. you cannot
multipley two Money instances, nor can you add a Money instance to a
non-Money number; dividing a Money instance by another results in a
Decimal value, etc.

The Currency class is provided with a complete dictionary of ISO 4217
currencies data, each key (e.g. 'USD') mapping to a Currency instance
with ISO numeric code, canonical name in English, and countries using
the currency.


Testing
--------

Unit-tests have been provided, and can be run with py.test.  This
version has been tested with Python 2.6.


Future
------

Future versions of py-money may provide currency conversions, or other
capabilities, dependent on feedback and usage.