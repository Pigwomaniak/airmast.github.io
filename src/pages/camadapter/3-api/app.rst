app
===

Reset video stream
------------------

.. class:: request-table-3

+--------------+------------------------------+-------------+
| Request Type |             URL              | DJI Zenmuse |
+==============+==============================+=============+
| POST         | **/api/v1/app/reset\_video** | Any         |
+--------------+------------------------------+-------------+

Sample Request
~~~~~~~~~~~~~~

.. code:: http

    POST http://localhost:8123/api/v1/app/reset_video

Sample Response
~~~~~~~~~~~~~~~

Status code: **200**

.. code:: javascript

    {
      "success": true
    }

Get application info
--------------------

.. class:: request-table-3

+--------------+-----------------+-------------+
| Request Type |       URL       | DJI Zenmuse |
+==============+=================+=============+
| GET          | **/api/v1/app** | Any         |
+--------------+-----------------+-------------+

JSON Response
~~~~~~~~~~~~~

.. class:: parameter-table-3

+-----------------------+--------+-------------------------------+
|       Parameter       |  Type  |          Description          |
+=======================+========+===============================+
| **build_date**        | string | Application build date        |
+-----------------------+--------+-------------------------------+
| **safe_sound**        | number | Counter from  0 to 255 that   |
|                       |        | increments every request      |
+-----------------------+--------+-------------------------------+
| **uptime**            | string | Time since  server start      |
+-----------------------+--------+-------------------------------+
| **version**           | string | Application version           |
+-----------------------+--------+-------------------------------+
| **video_connections** | number | Number of connections         |
|                       |        | to video stream               |
+-----------------------+--------+-------------------------------+
| **video_amount**      | number | Amount of video data          |
|                       |        | transferred (KiB)             |
+-----------------------+--------+-------------------------------+
| **video_rate**        | number | Speed of video stream (KiB/s) |
+-----------------------+--------+-------------------------------+
| **canbus_tx**         | number | Amount of data transmitted    |
|                       |        | by CAN bus (KiB)              |
+-----------------------+--------+-------------------------------+
| **canbus_rx**         | number | Amount of data received       |
|                       |        | by CAN bus (KiB)              |
+-----------------------+--------+-------------------------------+
| **zenmuse**           | string | Zenmuse model name.           |
|                       |        |                               |
|                       |        | Possible values:              |
|                       |        | ``x3``, ``x4s``, ``x5``,      |
|                       |        | ``x5r``, ``x5s``, ``xt``,     |
|                       |        | ``z3``, ``z30``               |
+-----------------------+--------+-------------------------------+

Sample Request
~~~~~~~~~~~~~~

.. code:: http

    GET http://localhost:8123/api/v1/app

Sample Response
~~~~~~~~~~~~~~~

Status code: **200**

.. code:: javascript

    {
      "build_date": "24.01.2017",
      "safe_sound": 89,
      "success": true,
      "uptime": "2 d, 03:35:08",
      "version": "v0.1.0 build 41"
      "video_connections":10,
      "video_amount": 1234,
      "video_rate": 123,
      "canbus_tx": 500,
      "canbus_rx": 600,
      "zenmuse": "x3",
    }
