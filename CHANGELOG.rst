Unreleased
----------

- Issue #28380: unittest.mock Mock autospec functions now properly support
  assert_called, assert_not_called, and assert_called_once.
  
- Issue #28735: Fixed the comparison of mock.MagickMock with mock.ANY.

- Issue #20804: The unittest.mock.sentinel attributes now preserve their
  identity when they are copied or pickled.

- Issue #28961: Fix unittest.mock._Call helper: don't ignore the name parameter
  anymore. Patch written by Jiajun Huang.

- Issue #26750: unittest.mock.create_autospec() now works properly for
  subclasses of property() and other data descriptors.

- Issue #21271: New keyword only parameters in reset_mock call.

- Issue #26807: mock_open 'files' no longer error on readline at end of file.
  Patch from Yolanda Robla.

- Issue #25195: Fix a regression in mock.MagicMock. _Call is a subclass of
  tuple (changeset 3603bae63c13 only works for classes) so we need to
  implement __ne__ ourselves.  Patch by Andrew Plummer.

2.0.0
-----

- Issue #26323: Add Mock.assert_called() and Mock.assert_called_once()
  methods to unittest.mock. Patch written by Amit Saha.

- Issue #22138: Fix mock.patch behavior when patching descriptors. Restore
  original values after patching. Patch contributed by Sean McCully.

- Issue #24857: Comparing call_args to a long sequence now correctly returns a
  boolean result instead of raising an exception.  Patch by A Kaptur.

- Issue #23004: mock_open() now reads binary data correctly when the type of
  read_data is bytes.  Initial patch by Aaron Hill.

- Issue #21750: mock_open.read_data can now be read from each instance, as it
  could in Python 3.3.

- Issue #18622: unittest.mock.mock_open().reset_mock would recurse infinitely.
  Patch from Nicola Palumbo and Laurent De Buyst.

- Issue #23661: unittest.mock side_effects can now be exceptions again. This
  was a regression vs Python 3.4. Patch from Ignacio Rossi

- Issue #23310: Fix MagicMock's initializer to work with __methods__, just
  like configure_mock().  Patch by Kasia Jachim.

- Issue #23568: Add rdivmod support to MagicMock() objects.
  Patch by Håkan Lövdahl.

- Issue #23581: Add matmul support to MagicMock. Patch by Håkan Lövdahl.

- Issue #23326: Removed __ne__ implementations.  Since fixing default __ne__
  implementation in issue #21408 they are redundant. *** NOT BACKPORTED ***

- Issue #21270: We now override tuple methods in mock.call objects so that
  they can be used as normal call attributes.

- Issue #21256: Printout of keyword args should be in deterministic order in
  a mock function call. This will help to write better doctests.

- Issue #21262: New method assert_not_called for Mock.
  It raises AssertionError if the mock has been called.

- Issue #21238: New keyword argument `unsafe` to Mock. It raises
  `AttributeError` incase of an attribute startswith assert or assret.

- Issue #21239: patch.stopall() didn't work deterministically when the same
  name was patched more than once.

- Issue #21222: Passing name keyword argument to mock.create_autospec now
  works.

- Issue #17826: setting an iterable side_effect on a mock function created by
  create_autospec now works. Patch by Kushal Das.

- Issue #17826: setting an iterable side_effect on a mock function created by
  create_autospec now works. Patch by Kushal Das.

- Issue #20968: unittest.mock.MagicMock now supports division.
  Patch by Johannes Baiter.

- Issue #20189: unittest.mock now no longer assumes that any object for
  which it could get an inspect.Signature is a callable written in Python.
  Fix courtesy of Michael Foord.

- Issue #17467: add readline and readlines support to mock_open in
  unittest.mock.

- Issue #17015: When it has a spec, a Mock object now inspects its signature
  when matching calls, so that arguments can be matched positionally or
  by name.

- Issue #15323: improve failure message of Mock.assert_called_once_with

- Issue #14857: fix regression in references to PEP 3135 implicit __class__
  closure variable (Reopens issue #12370)

- Issue #14295: Add unittest.mock
