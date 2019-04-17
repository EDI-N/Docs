**Проверки активности**
============

Проверка активности сервера:

.. code:: ruby

    curl -X GET 'https://edo-v2.edi-n.com/ping'

Проверка активности сессии:

.. code:: ruby

    curl -X GET 'https://edo-v2.edi-n.com/api/auth_check' -b 'SID=65daca25-74ba-4c85-8183-71b404a348c0;'

--------------