Auptimizer Quickstart
=====================

|GPL 3.0 License| |pipeline status| |coverage report| |repo url|

**Auptimizer** is an optimization tool for Machine Learning (ML) that automates many of the tedious parts of the model building process.
Currently, **Auptimizer** helps with:

-  **Automating tedious experimentation** - Start using Auptimizer by
   changing just a few lines of your code. It will run and record the
   sophisticated hyperparameter optimization (HPO) experiments for you,
   resulting in effortless consistency and reproducibility.

-  **Making the best use of your compute-resources** - Whether you are
   using a couple of GPUs or AWS, Auptimizer will help you orchestrate
   compute resources for faster hyperparameter tuning.

-  **Getting the best models in minimum time** - Generate optimal models
   and achieve better performance by employing state-of-the-art HPO
   techniques. Auptimizer provides a single seamless access point to
   top-notch HPO algorithms, including Bayesian optimization and
   multi-armed bandit. You can even integrate your own proprietary solution.

Best of all, **Auptimizer** offers a consistent interface that allows
users to switch between different HPO algorithms and computing resources
with minimal changes to their existing code.

As development progress, **Auptimizer** will support the end-to-end
development cycle for building models for edge devices including robust
support for model compression and neural architecture search. The table
below shows a full list of currently supported techniques.

+----------------------------------------------------------------+-----------------------------------+
| Supported HPO Algorithms                                       | Supported Infrastructure          |
+================================================================+===================================+
| | Random                                                       | | Multiple CPUs                   |
| | Grid                                                         | | Multiple GPUs                   |
| | `Hyperband <https://github.com/zygmuntz/hyperband>`__        | | Multiple Machines (SSH)         |
| | `Hyperopt <https://github.com/hyperopt/hyperopt>`__          | | EC2 instances                   |
| | `Spearmint <https://github.com/JasperSnoek/spearmint>`__     |                                   |
| | `BOHB <https://github.com/automl/HpBandSter>`__              |                                   |
| | `EAS (experimental) <https://github.com/han-cai/EAS>`__      |                                   |
| | Passive                                                      |                                   |
+----------------------------------------------------------------+-----------------------------------+

Install
-------

**Auptimizer** currently is well tested on Linux systems, it may require
some tweaks for Windows users by their own.

::

   pip install auptimizer

**Note** Dependencies are not included. Using ``pip install``
`requirements.txt <https://github.com/LGE-ARC-AdvancedAI/auptimizer/blob/master/requirements.txt>`_ will install
necessary libraries for all functionalities.

Documentation
-------------

See more in `documentation <https://lge-arc-advancedai.github.io/auptimizer/>`__

Example
-------

::

   cd Examples/demo
   # Setup environment (Interactively create the environment file based on user input)
   python -m aup.setup
   # Setup experiment
   python -m aup.init
   # Create training script - auto.py
   python -m aup.convert origin.py experiment.json demo_func
   # Run aup for this experiment
   python -m aup experiment.json

Each job’s hyperparameter configuration is saved separately under
``jobs/*.json`` and is also recorded in the SQLite file
``.aup/sqlite3.db``.

.. figure:: ./images/demo.gif
   :alt: demo

License
-------

`GPL 3.0 License <./LICENSE>`__

.. |GPL 3.0 License| image:: https://img.shields.io/badge/License-GPL%203.0-blue.svg
    :target: https://opensource.org/licenses/GPL-3.0
.. |pipeline status| image:: https://travis-ci.org/LGE-ARC-AdvancedAI/auptimizer.svg?branch=master
   :target: https://travis-ci.org/LGE-ARC-AdvancedAI/auptimizer
.. |coverage report| image:: https://codecov.io/gh/LGE-ARC-AdvancedAI/auptimizer/branch/master/graph/badge.svg
   :target: https://codecov.io/gh/LGE-ARC-AdvancedAI/auptimizer
.. |repo url| image:: https://img.shields.io/badge/github-repo-information.svg
    :target: https://github.com/LGE-ARC-AdvancedAI/auptimizer


Cite
----

If you have used this software for research, please cite the following paper (accepted at IEEE Big Data 2019):

.. code-block:: none

   @misc{liu2019auptimizer,
    title={Auptimizer -- an Extensible, Open-Source Framework for Hyperparameter Tuning},
    author={Jiayi Liu and Samarth Tripathi and Unmesh Kurup and Mohak Shah},
    year={2019},
    eprint={1911.02522},
    archivePrefix={arXiv},
    primaryClass={cs.LG}
   }