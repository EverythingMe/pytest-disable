pytest-disable
==============

pytest plugin to disable a test and skip it from testrun.

Install with:

    pip install pytest-disable

Usage:

    import pytest

    @pytest.mark.disable(reason='Test is flaky and fails')
    def test_foo():
        assert True==False

    def test_bar():
        assert True

Yields this output:

    $ py.test -sv test_foo.py
    ===================================== test session starts ======================================
    platform darwin -- Python 2.7.10 -- py-1.4.30 -- pytest-2.7.10 -- /usr/bin/python
    plugins: disable
    collected 2 items

    test_foo.py::test_foo SKIPPED
    test_foo.py::test_bar PASSED

    =================================== short test summary info ====================================
    SKIP [1] test_foo.py:3: Test is flaky and fails.
    ============================= 1 passed, 1 skipped in 0.01 seconds ==============================