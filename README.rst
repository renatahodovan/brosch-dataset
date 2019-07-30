======================
BroSCH Dataset (r2018)
======================
*Browser Security Commit History Dataset*


This repository contains the dataset mined by the BroSCH_ tool (version 19.7)
from the commit histories and issue trackers of two open source browser
projects, WebKit_ and Firefox_, up until the end of year 2018.

.. _BroSCH: https://github.com/renatahodovan/brosch
.. _WebKit: https://webkit.org
.. _Firefox: https://www.mozilla.org/en-US/firefox/

The dataset was generated with the following commands::

    ./brosch.py -b webkit collect -r ./WebKit --before "2019-01-01 00:00:00"
    ./brosch.py -b webkit identify --retry 2
    ./brosch.py -b webkit match -r ./WebKit --before "2019-01-01 00:00:00"

    ./brosch.py -b firefox collect -r ./gecko-dev --before "2019-01-01 00:00:00"
    ./brosch.py -b firefox identify --retry 2
    ./brosch.py -b firefox match -r ./gecko-dev --before "2019-01-01 00:00:00"

The dataset is in JSON_ format conforming to the BroSCH schema_. (For its
interpretation, see the `JSON Schema`_ specification.) The dataset contains
commit IDs, author dates, committed dates, and lists of referenced issue IDs.
To extend it with information like author name, commiter name, and commit
message details, see the usage notes of the BroSCH_ tool.

.. _JSON: https://www.json.org
.. _JSON Schema: https://json-schema.org
.. _schema: brosch-schema.json

The dataset is licensed under the BSD 3-Clause License_.

.. _License: LICENSE.rst
