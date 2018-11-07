
QIT - a quantum ready machine learning platform
------------

The qindomClient SDK is an open source tool built on top of python that provides API connections to QIT services. 

With minimal configuration, you can start using all of the machine learning algorithms that natively designed and implemented by the Qindom team. 

QIT is designed to serve Quantum Machine Learning methods and algorithm to public, and we are dedicated to build a whole new ML/AL eco-system.

Installation
------------
1. Make sure you have python 3.7.0 or greater (or else python 2.7).

    See [Installing Python 3](https://docs.python-guide.org/) @ the hitchhiker's guide to python.

2. Use `pip` to install `qindomClient`:

    ```bash
    pip install --upgrade pip
    pip install qindomClient
    ```

Account sign up
------------

Contact info@qindom.com to get 
qit_access_user_name;  qit_access_secrect_key;  aws_access_key_id;  aws_secret_access_key

Install aws cli on your windows or linux
https://docs.aws.amazon.com/cli/latest/userguide/installing.html

In your windows command line interface or linux terminal run aws configure, use aws_access_key_id  aws_secret_access_key to finish configuring

Data preparation
------------

Two kinds of data should be prepared. 

One is training data, with no index, no column header, and prediction result in the last column. 

The other is prediction data, with no index, no column header, no prediction result.

Sample code
-----------

A simple example to get you up and running
https://github.com/Qindom/QIT/blob/master/Sample.ipynb

Disclaimers
----------
**Qit is currently in alpha.** We are still making breaking changes, and we *will* break your code when we make new releases. We recommend that you pin a specific version of qindomClient in `requirements.txt` files, and periodically bump to the latest release. That way you have control over when a breaking change affects you.

<p>
  
**Copyright 2018 Qindom Inc.**

