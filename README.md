[![Testspace](https://www.testspace.com/img/Testspace.png)](https://www.testspace.com)

***

## Python/Unittest sample for demonstrating Testspace based on the [test_driven_python repo](https://github.com/siddhi/test_driven_python)

Sample demonstrates techniques for using Testspace with Python code and the [`unittest` test framework](https://docs.python.org/2/library/unittest.html) together with [`cov-core` code coverage tool](https://pypi.python.org/pypi/cov-core) and [`nose2` runner](https://github.com/nose-devs/nose2).

  * Using a Testspace Project that is `connected` with this GitHub Repo
  * Using 3 Online CI services for demonstration purposes only
  * Can review the Results at [testspace-samples:python.unittest](https://samples.testspace.com/projects/testspace-samples:python.unittest)
  * Refer to our [Help](https://help.testspace.com/) for more information


***
Using Multiple Online CI Services:

![Build](https://github.com/testspace-samples/python.unittest/workflows/Build/badge.svg)
[![Build Status](https://travis-ci.org/testspace-samples/python.unittest.svg?branch=master)](https://travis-ci.org/testspace-samples/python.unittest)
[![CircleCI](https://circleci.com/gh/testspace-samples/python.unittest.svg?style=svg)](https://circleci.com/gh/testspace-samples/python.unittest)


***
Publishing **Test Content** using www.testspace.com.

[![Space Health](https://samples.testspace.com/spaces/757/badge?token=61c13f97c367398a2b23fcbff3d7dc4ff8980f94)](https://samples.testspace.com/spaces/757?utm_campaign=badge&utm_medium=referral&utm_source=test "Test Cases")
[![Space Metric](https://samples.testspace.com/spaces/757/metrics/683/badge?token=116815d4171e04500825d50efd8faae6795a50dd)](https://samples.testspace.com/spaces/757/schema/Code%20Coverage?utm_campaign=badge&utm_medium=referral&utm_source=coverage "Code Coverage (lines)")
[![Space Metric](https://samples.testspace.com/spaces/757/metrics/684/badge?token=ccdfd31aa029f081c99f3b2748b7fa3714de4410)](https://samples.testspace.com/spaces/757/schema/Static%20Analysis?utm_campaign=badge&utm_medium=referral&utm_source=analysis "Static Analysis (issues)")

***

In order to run this sample you will need a host workstation with installed python 2.6+.


Download and configure the Testspace client
<pre>
mkdir -p $HOME/bin
curl -s https://testspace-client.s3.amazonaws.com/testspace-linux.tgz | tar -zxvf- -C $HOME/bin
testspace config url samples.testspace.com
</pre>


Buiding:
<pre>
sudo pip install -r requirements.txt
sudo apt-get install pylint
</pre>


Running Static Analysis:
<pre>
pylint stock_alerter/ -f parseable > analysis.txt
</pre>

Running Tests with Code Coverage:

<pre>
nose2 --junit-xml --with-coverage
</pre>

Push Content using Testspace client

<pre>
testspace analysis.txt{lint} nose2.xml{stock_alerter} coverage.xml
</pre>

