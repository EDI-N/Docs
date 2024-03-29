######################################################################
**Получение списка всех сетей**
######################################################################

Для работы с этим методом пользователь должен быть `авторизированным <https://wiki.edi-n.com/ru/latest/integration_2_0/API/Authorization.html>`__ .

С помощью метода **api/oas/allretailers** можно получить список всех сетей, связанным с авторизованным пользователем.

+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
|                      **Метод запроса**                      |                                              **HTTP GET**                                              |
+=============================================================+========================================================================================================+
| **Content-Type**                                            | application/json (тело запроса/ответа в json формате в теле HTTP запроса                               |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
| **URL запроса**                                             | https://edo-v2.edi-n.com/api/oas/allretailers                                                          |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+
| **Параметры, передаваемые в URL (вместе с адресом метода)** | В строке заголовка (Header) "Cookie" обязательно передается **SID** - токен полученный при авторизации |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------+

.. hint:: Также возможно выполнить запрос в виде curl-строки:
          
        curl -X GET 'https://edo-v2.edi-n.com/api/oas/allretailers' -b 'SID=65daca25-74ba-4c85-8183-71b404a348c0;'

Спецификация для расшифровки ключей curl запроса: https://curl.haxx.se/docs/manpage.html

--------------

**JSON-параметры в теле HTTP запроса/ответа**

--------------

**REQUEST**

--------------

В этом методе json-тело **запроса** отсутствует (другие данные передавать не нужно).

--------------

**RESPONSE**

--------------

Таблица 1 - Описание json-параметров, которые могут передаваться в **ответ** на метод API

+--------------+------------+---------------------------------------+
| **Параметр** | **Формат** |             **Описание**              |
+==============+============+=======================================+
| id           | число      | идентификатор розничной сети          |
+--------------+------------+---------------------------------------+
| name         | строка     | имя розничной сети                    |
+--------------+------------+---------------------------------------+
| gln          | строка(13) | номер GLN организации                 |
+--------------+------------+---------------------------------------+
| aliasName    | строка     | бренд ТС, альтернативное имя          |
+--------------+------------+---------------------------------------+
| type         | число      | тип сети, 1 - прямая, 2 - роуминговая |
+--------------+------------+---------------------------------------+

--------------

**Примеры**

--------------

При использовании метода **api/oas/allretailers** json-тело **запроса** отсутствует (данные передавать не нужно).

**Пример тела ответа (json):**

.. code:: ruby

  [
    {
      "id": 7,
      "name": "Варус (ОМЕГА)",
      "gln": "4820110632160",
      "aliasName": "Варус(ОМЕГА))",
      "type": 1
    },
    {
      "id": 8,
      "name": "Старый Колос",
      "gln": "4829900003845",
      "aliasName": "Олд_Колос",
      "type": 1
    },
    {
      "id": 9,
      "name": "АТБ-маркет",
      "gln": "4820128010004",
      "aliasName": "АТБ-маркет",
      "type": 1
    },
    {
      "id": 17297,
      "name": "Интеграция",
      "gln": "1234567890123",
      "aliasName": "Интеграция",
      "type": 2
    }
  ] 

