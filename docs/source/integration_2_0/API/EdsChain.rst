######################################################################
Получение конкретной цепочки документов
######################################################################

Для работы с этим методом пользователь должен быть `авторизированным <https://ссылка на авторизацию>`__ .

С помощью метода **api/eds/chain** и задаваемых параметров получить (выгрузить) необходимые данные конкретной цепочки документов.

+-------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
|                      **Метод запроса**                      |                                                                                                  **HTTP GET**                                                                                                   |
+=============================================================+=================================================================================================================================================================================================================+
| **Content-Type**                                            | application/json (тело запроса/ответа в json формате в теле HTTP запроса                                                                                                                                        |
+-------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **URL запроса**                                             | https://edo-v2.edi-n.com/api/eds/chain?gln=9864065702429&chain_uuid=9fe45d32-35c7-44d0-9131-7257fc0c0f39&load_docs=true&load_bodies=true&load_package=true&load_comments=true&load_tags=true&load_statuses=true |
+-------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| **Параметры, передаваемые в URL (вместе с адресом метода)** | В строке заголовка (Header) "Set-Cookie" обязательно передается **SID** - токен полученный при авторизации                                                                                                      |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **Обязательные url-параметры:**                                                                                                                                                                                 |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **gln** - строка(13); номер GLN организации, которая связана с авторизированным пользователем платформы EDIN 2.0 на уровне аккаунта                                                                             |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **chain_uuid** - строка; ID цепочки                                                                                                                                                                             |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **Опциональные url-параметры (boolean фильтры):**                                                                                                                                                               |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **load_docs** - загружать ли документы относящиеся к цепочке                                                                                                                                                    |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **load_bodies** - загружать ли тела документов                                                                                                                                                                  |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **load_package** - загружать ли пакеты                                                                                                                                                                          |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **load_comments** - загружать ли комментарии                                                                                                                                                                    |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **load_tags** - загружать ли теги к документам                                                                                                                                                                  |
|                                                             |                                                                                                                                                                                                                 |
|                                                             | **load_statuses** - загружать ли статусы к документам                                                                                                                                                           |
+-------------------------------------------------------------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

.. hint:: Также возможно выполнить запрос в виде curl-строки:
          
          curl -X GET 'https://edo-v2.edi-n.com/api/eds/chain?gln=9864065702429&chain_uuid=9fe45d32-35c7-44d0-9131-7257fc0c0f39&load_docs=true&load_bodies=true&load_package=true&load_comments=true&load_tags=true&load_statuses=true' -b 'SID=458a0d38-5b56-4b8e-8998-009a1edd31eb'

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

Таблица 4 - Описание json-параметров, которые могут передаваться в **ответ** на метод API

.. csv-table:: 
  :file: for_csv/XChain.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 1

Таблица 5 - Описание параметров объекта **XChainStatus**)

.. csv-table:: 
  :file: for_csv/XChainStatus.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 1

Таблица 6 - Описание параметров объекта **XDocStatus**)

.. csv-table:: 
  :file: for_csv/XDocStatus.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 7 - Описание параметров объекта **XDoc**)

.. csv-table:: 
  :file: for_csv/XDoc.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 8 - Описание параметров объекта **XTag**)

.. csv-table:: 
  :file: for_csv/XTag.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 9 - Описание параметров объекта **XStatus**)

.. csv-table:: 
  :file: for_csv/XStatus.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 10 - Описание параметров объекта **XDocSignInfo**)

.. csv-table:: 
  :file: for_csv/XDocSignInfo.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 11 - Описание параметров объекта **XDocCommentsList**)

.. csv-table:: 
  :file: for_csv/XDocCommentsList.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 12 - Описание параметров объекта **XDocComment**)

.. csv-table:: 
  :file: for_csv/XDocComment.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 13 - Описание параметров объекта **XDocAttachment**)

.. csv-table:: 
  :file: for_csv/XDocAttachment.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 14 - Описание параметров объекта **XDocBodyForms**)

.. csv-table:: 
  :file: for_csv/XDocBodyForms.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 15 - Описание параметров объекта **XDocBody**)

.. csv-table:: 
  :file: for_csv/XDocBody.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 16 - Описание параметров объекта **XDocBodyType**)

.. csv-table:: 
  :file: for_csv/XDocBodyType.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 17 - Описание параметров объекта **XDocType**)

.. csv-table:: 
  :file: for_csv/XDocType.csv
  :widths:  1, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

.. _подробнее:

Таблица 18 - Описание **DocStatus** параметров (объект XDocStatus_)

.. csv-table:: 
  :file: for_csv/xdocstatus_p.csv
  :widths:  1, 60
  :header-rows: 1
  :stub-columns: 0

.. _описание_параметров:

Таблица 19 - Описание **DocType** параметров (объект XDocType_)

.. csv-table:: 
  :file: for_csv/xdoctype_p.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0


--------------

**Примеры**

--------------

**Запрос не содержит тела (json)**

**Примеры url-запросов:**

**Получить перечень документов по определенной цепочке без загрузки их тел, пакетов, комментариев, тегов и статусов**
=======================================================================================================================

  https://edo-v2.edi-n.com/api/eds/chain?gln=9864232304302&chain_uuid=0fe60377-51db-4b7a-b7eb-cdf5fa91a46a&load_docs=true&load_bodies=false&load_package=false&load_comments=false&load_tags=false&load_statuses=false

**Получить перечень документов по определенной цепочке с загрузкой тел и комментариев без загрузки их пакетов, тегов и статусов**
====================================================================================================================================

  https://edo-v2.edi-n.com/api/eds/chain?gln=9864232304302&chain_uuid=0fe60377-51db-4b7a-b7eb-cdf5fa91a46a&load_docs=true&load_bodies=true&load_package=false&load_comments=true&load_tags=false&load_statuses=false

**Получить перечень документов по определенной цепочке с загрузкой пакетов, тегов без загрузки их тел и комментариев и статусов**
====================================================================================================================================

  https://edo-v2.edi-n.com/api/eds/chain?gln=9864232304302&chain_uuid=0fe60377-51db-4b7a-b7eb-cdf5fa91a46a&load_docs=true&load_bodies=false&load_package=true&load_comments=false&load_tags=true&load_statuses=false

**Получить перечень документов по определенной цепочке с загрузкой статусов  без загрузки их тел, комментариев, пакетов, тегов** 
====================================================================================================================================

  https://edo-v2.edi-n.com/api/eds/chain?gln=9864232304302&chain_uuid=0fe60377-51db-4b7a-b7eb-cdf5fa91a46a&load_docs=true&load_bodies=false&load_package=false&load_comments=false&load_tags=false&load_statuses=true

--------------

**Пример тела ответа (json):**

.. code:: ruby

    {
        "id": 1,
        "uuid": "0fe60377-51db-4b7a-b7eb-cdf5fa91a46a",
        "packageID": 0,
        "type": {
            "type": 5,
            "title": "ordrsp",
            "description": "Подтверждение заказа"
        },
        "docsCount": 13,
        "lastInDocID": 1,
        "lastOutDocID": 29,
        "partnerId": 0,
        "important": false,
        "status": {
            "status": 2,
            "title": "sent"
        },
        "visualStatus": 0,
        "archive": false,
        "childs": [
            {
                "body": {
                    "forms": {}
                },
                "attachments": [],
                "comments": [],
                "doc_id": 1,
                "doc_uuid": "bf8dacb1-7b61-4c9c-ab36-ac37620db051",
                "uuidSender": "9864232304319",
                "uuidReceiver": "9864232304302",
                "docNumber": "1001",
                "dateCreated": 1555487166,
                "dateChanged": 1555487166,
                "dateRead": 1555497325,
                "docDate": 1555448400,
                "chain_id": 1,
                "chain_uuid": "0fe60377-51db-4b7a-b7eb-cdf5fa91a46a",
                "family": 1,
                "hash": "A1FF5B519289B936A09E99514277F429",
                "type": {
                    "type": 2,
                    "title": "orders",
                    "description": "Заказ"
                },
                "status": {
                    "status": 5,
                    "title": "read"
                },
                "exchange_status": "000000000000000000000000",
                "is_archive": false,
                "extraFields": {
                    "sub_doc_type_id": "2",
                    "buyer_uuid": "9864232304319",
                    "doc_num": "1001",
                    "order_number": "1001",
                    "ftpex_file_date": "1555487160",
                    "supplier_uuid": "9864232304302",
                    "delivery_place_uuid": "9864232304562",
                    "order_date": "1555448400",
                    "delivery_date": "1556485200",
                    "ftpex_file_name": "order_20190417104600_475593380.xml",
                    "contract_number": "Дог 1",
                    "sender": "9864232304319",
                    "doc_date": "1555448400",
                    "recipient": "9864232304302",
                    "action": "0"
                },
                "tags": [],
                "statuses": [],
                "multiExtraFields": {}
            },

            ...
            
            {
                "body": {
                    "forms": {}
                },
                "attachments": [],
                "comments": [],
                "doc_id": 29,
                "doc_uuid": "cb2f183f-ccbc-467b-9eb2-90b2c1ff8f5c",
                "uuidSender": "9864232304302",
                "uuidReceiver": "9864232304319",
                "docNumber": "АФ00-000001",
                "dateCreated": 1556115021,
                "dateChanged": 1556115022,
                "dateRead": 0,
                "docDate": 1556116482,
                "chain_id": 1,
                "chain_uuid": "0fe60377-51db-4b7a-b7eb-cdf5fa91a46a",
                "family": 1,
                "hash": "0F9CEEC0717992EB76A848F2E106D2D0",
                "type": {
                    "type": 5,
                    "title": "ordrsp",
                    "description": "Подтверждение заказа"
                },
                "status": {
                    "status": 2,
                    "title": "sent"
                },
                "exchange_status": "000000000000000000000000",
                "is_archive": false,
                "extraFields": {
                    "order_date": "1555448400",
                    "delivery_date": "1556485200",
                    "contract_number": "Дог 1",
                    "sender": "9864232304319",
                    "buyer_uuid": "9864232304319",
                    "doc_num": "АФ00-000001",
                    "order_number": "1001",
                    "doc_date": "1556116482",
                    "action": "4",
                    "supplier_uuid": "9864232304302",
                    "delivery_place_uuid": "9864232304562"
                },
                "tags": [],
                "statuses": [],
                "multiExtraFields": {}
            }
        ],
        "hash": "ABB416F3FF3B5027D212D62DD9F99E94"
    }




