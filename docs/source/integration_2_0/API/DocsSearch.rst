######################################################################
Поиск документов (с фильтрацией), выбор списка документов
######################################################################

Для работы с этим методом пользователь должен быть `авторизированным <https://ссылка на авторизацию>`__ .

С помощью метода **api/eds/docs/search** можно быстро совершить поиск по заданым критериям, например, получить список документов с определенным статусом, или за промежуток времени.

+-------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
|                      **Метод запроса**                      |                                                            **HTTP POST**                                                            |
+=============================================================+=====================================================================================================================================+
| **Content-Type**                                            | application/json (тело запроса/ответа в json формате в теле HTTP запроса                                                            |
+-------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
| **URL запроса**                                             | https://edo-v2.edi-n.com/api/eds/docs/search?gln=9864065702429                                                                      |
+-------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+
| **Параметры, передаваемые в URL (вместе с адресом метода)** | В строке заголовка (Header) "Set-Cookie" обязательно передается **SID** - токен полученный при авторизации                          |
|                                                             |                                                                                                                                     |
|                                                             | **Обязательные url-параметры:**                                                                                                     |
|                                                             |                                                                                                                                     |
|                                                             | **gln** - строка(13); номер GLN организации, которая связана с авторизированным пользователем платформы EDIN 2.0 на уровне аккаунта |
|                                                             |                                                                                                                                     |
|                                                             | {"…"} - тело http запроса - json с критериями поиска (Таблица_2_)                                                                   |
+-------------------------------------------------------------+-------------------------------------------------------------------------------------------------------------------------------------+

**Внимание:** В запросе в теле json присутствуют обязательные (должны передаваться) и опциональные параметры (колонка Тип_).

.. hint:: Также возможно выполнить запрос в виде curl-строки:
          
          curl -X POST 'https://edo-v2.edi-n.com/api/eds/docs/search?gln=9864065702429' -d {json с критериями поиска(Таблица_2_)} -b 'SID=458a0d38-5b56-4b8e-8998-009a1edd31eb'

Спецификация для расшифровки ключей curl запроса: https://curl.haxx.se/docs/manpage.html

--------------

**JSON-параметры в теле HTTP запроса/ответа**

--------------

**REQUEST**

--------------

.. _Таблица_2:

Таблица 2 - Описание json-параметров (фильтр) **запроса** метода API

.. csv-table:: 
  :file: for_csv/StorageQuery.csv
  :widths:  1, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 3 - Описание параметров объекта **ExtraQueryParameters**

.. csv-table:: 
  :file: for_csv/ExtraQueryParameters.csv
  :widths:  1, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 4 - Описание параметров объекта **Direction**

.. csv-table:: 
  :file: for_csv/Direction.csv
  :widths:  1, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 5 - Описание параметров объекта **Limitation**

.. csv-table:: 
  :file: for_csv/Limitation.csv
  :widths:  1, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 6 - Описание параметров объекта **DateTimeRange**

.. csv-table:: 
  :file: for_csv/DateTimeRange.csv
  :widths:  1, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 7 - Описание параметров объекта **XDocType**

.. csv-table:: 
  :file: for_csv/XDocType.csv
  :widths:  1, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

.. _fieldName:

Таблица 8 - Описание **fieldName** параметров (объект ExtraQueryParameters_)

.. csv-table:: 
  :file: for_csv/extra_fields.csv
  :widths:  1, 2, 7, 12, 41
  :header-rows: 1
  :stub-columns: 0

.. _описание_параметров:

Таблица 9 - Описание **DocType** параметров (объект XDocType_)

.. csv-table:: 
  :file: for_csv/xdoctype_p.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

.. _Тип:

***Тип*** поля: **M** - mandatory (обязательное к заполнению), **O** - optional (опциональное)

--------------

**RESPONSE**

--------------

Таблица 10 - Описание json-параметров, которые могут передаваться в **ответ** на метод API

.. csv-table:: 
  :file: for_csv/XDoc+.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 11 - Описание параметров объекта **XDocStatus**

.. csv-table:: 
  :file: for_csv/XDocStatus.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 12 - Описание параметров объекта **XDoc**

.. csv-table:: 
  :file: for_csv/XDoc.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 13 - Описание параметров объекта **XTag**

.. csv-table:: 
  :file: for_csv/XTag.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 14 - Описание параметров объекта **XStatus**

.. csv-table:: 
  :file: for_csv/XStatus.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 15 - Описание параметров объекта **XDocSignInfo**

.. csv-table:: 
  :file: for_csv/XDocSignInfo.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 16 - Описание параметров объекта **XDocCommentsList**

.. csv-table:: 
  :file: for_csv/XDocCommentsList.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 17 - Описание параметров объекта **XDocComment**

.. csv-table:: 
  :file: for_csv/XDocComment.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 18 - Описание параметров объекта **XDocAttachment**

.. csv-table:: 
  :file: for_csv/XDocAttachment.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 19 - Описание параметров объекта **XDocBodyForms**

.. csv-table:: 
  :file: for_csv/XDocBodyForms.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 20 - Описание параметров объекта **XDocBody**

.. csv-table:: 
  :file: for_csv/XDocBody.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

Таблица 21 - Описание параметров объекта **XDocBodyType**

.. csv-table:: 
  :file: for_csv/XDocBodyType.csv
  :widths:  1, 19, 41
  :header-rows: 1
  :stub-columns: 0

.. _подробнее:

Таблица 22 - Описание **DocStatus** параметров (объект XDocStatus_)

.. csv-table:: 
  :file: for_csv/xdocstatus_p.csv
  :widths:  1, 60
  :header-rows: 1
  :stub-columns: 0


--------------

**Примеры (json)**

--------------

**Получить все входящие (полученные) документы на определенный GLN без черновиков (массив statuses не содержит "1")**
=======================================================================================================================

.. code:: ruby

    {
        "direction": {
            "sender": [],
            "receiver": [
                "9864232304302"
            ],
            "type": "IN"
        },
        "exchangeStatus": [],
        "family": "1",
        "statuses": [
            "2",
            "3",
            "4",
            "5",
            "6",
            "7"
        ],
        "type": [
            {
                "type": "0"
            }
        ]
    }

**Получить все исходящие (отправленные) документы по GLN без черновиков (массив statuses не содержит "1")**
=============================================================================================================

.. code:: ruby

    {
        "direction": {
            "sender": [
                "9864232304302"
            ],
            "receiver": [],
            "type": "IN"
        },
        "exchangeStatus": [],
        "family": "1",
        "statuses": [
            "2",
            "3",
            "4",
            "5",
            "6",
            "7"
        ],
        "type": [
            {
                "type": "0"
            }
        ]
    }

**Получить все входящие (полученные) документы на определенный GLN без черновиков (массив statuses не содержит "1"), у которых номер содержит подстроку "1001"**
===================================================================================================================================================================

.. code:: ruby

    {
        "direction": {
            "sender": [],
            "receiver": [
                "9864232304302"
            ],
            "type": "IN"
        },
        "exchangeStatus": [],
        "family": "1",
        "statuses": [
            "2",
            "3",
            "4",
            "5",
            "6",
            "7"
        ],
        "number": "1001",
        "type": [
            {
                "type": "0"
            }
        ]
    }

**Получить все исходящие (отправленные) документы по GLN без черновиков (массив statuses не содержит "1"), которые созданы в мае 2019 (startTimestamp и finishTimestamp даты в формате UNIX-timestamp)**
=========================================================================================================================================================================================================

.. code:: ruby

    {
        "direction": {
            "sender": [
                "9864232304302"
            ],
            "receiver": [],
            "type": "IN"
        },
        "exchangeStatus": [],
        "family": "1",
        "statuses": [
            "2",
            "3",
            "4",
            "5",
            "6",
            "7"
        ],
        "type": [
            {
                "type": "0"
            }
        ],
        "docDate": {
            "startTimestamp": "1556668800",
            "finishTimestamp": "1559347199"
        }
    }

--------------

**Пример тела ответа (json):**

.. code:: ruby

    {
        "items": [
            {
                "body": {
                    "forms": {}
                },
                "attachments": [],
                "comments": [],
                "doc_id": 1017,
                "doc_uuid": "e18a05d5-983b-4ebc-95f3-c35eccc7d611",
                "uuidSender": "4820128010004",
                "uuidReceiver": "9864065702429",
                "docNumber": "8663c3f48bea4f96a281238e847b1639",
                "dateCreated": 1549961913,
                "dateChanged": 1549961913,
                "dateRead": 0,
                "docDate": 1547503200,
                "chain_id": 1006,
                "chain_uuid": "60e487d3-871f-4b3a-9254-1d3f0e7a032f",
                "family": 1,
                "hash": "30745386780343D0C2F4C65C7F06D60F",
                "type": {
                    "type": 1,
                    "title": "invoice",
                    "description": "Счет"
                },
                "status": {
                    "status": 4,
                    "title": "inbox"
                },
                "exchange_status": "000000000000000000000000",
                "is_archive": false,
                "extraFields": {
                    "order_date": "1551477600",
                    "delivery_date": "1547503200",
                    "ftpex_file_name": "highload_invoice_test.xml",
                    "sender": "4820128010004",
                    "buyer_uuid": "4820128010004",
                    "doc_num": "8663c3f48bea4f96a281238e847b1639",
                    "order_number": "747401",
                    "doc_date": "1547503200",
                    "recipient": "9864065702429",
                    "ftpex_file_date": "1549961913",
                    "supplier_uuid": "9864065702429",
                    "delivery_place_uuid": "4820128019007"
                },
                "tags": [],
                "statuses": [],
                "multiExtraFields": {}
            }
        ],
        "totalCount": 0
    } 




