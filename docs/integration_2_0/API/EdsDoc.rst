######################################################################
**Создание черновика документа**
######################################################################

Для работы с этим методом пользователь должен быть `авторизированным <https://wiki.edi-n.com/ru/latest/integration_2_0/API/Authorization.html>`__ .

С помощью метода **api/eds/doc** можно быстро создать черновик документа конкретного указанного типа для конкретного получателя.

+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
|                      **Метод запроса**                      |                                                                  **HTTP POST**                                                                   |
+=============================================================+==================================================================================================================================================+
| **Content-Type**                                            | application/json (тело запроса/ответа в json формате в теле HTTP запроса                                                                         |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
| **URL запроса**                                             | https://edo-v2.edi-n.com/api/eds/doc?gln=9864065702429&doc_type=orders&doc_number=sdsd334&doc_date=1505497243&recipient=9864065702428&family=edi |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+
| **Параметры, передаваемые в URL (вместе с адресом метода)** | В строке заголовка (Header) "Cookie" обязательно передается **SID** - токен полученный при авторизации                                           |
|                                                             |                                                                                                                                                  |
|                                                             | **Обязательные url-параметры:**                                                                                                                  |
|                                                             |                                                                                                                                                  |
|                                                             | **gln** - строка(13); номер GLN организации, которая связана с авторизированным пользователем платформы EDIN 2.0 на уровне аккаунта              |
|                                                             |                                                                                                                                                  |
|                                                             | **doc_type** - строка; конкретный тип документа                                                                                                  |
|                                                             |                                                                                                                                                  |
|                                                             | **doc_number** - строка; номер документа                                                                                                         |
|                                                             |                                                                                                                                                  |
|                                                             | **doc_date** - число; дата документа (в формате UNIX-timestamp)                                                                                  |
|                                                             |                                                                                                                                                  |
|                                                             | **recipient** - строка(13); gln получателя                                                                                                       |
|                                                             |                                                                                                                                                  |
|                                                             | **family** - строка; "группа" документов, возможные значения:                                                                                    |
|                                                             | - edi                                                                                                                                            |
|                                                             | - uzd                                                                                                                                            |
|                                                             | - reports                                                                                                                                        |
|                                                             | - certificats                                                                                                                                    |
|                                                             | - factoring                                                                                                                                      |
|                                                             |                                                                                                                                                  |
|                                                             | {"…"} - тело http запроса - json документа                                                                                                       |
+-------------------------------------------------------------+--------------------------------------------------------------------------------------------------------------------------------------------------+

.. hint:: Также возможно выполнить запрос в виде curl-строки:
          
          curl -X POST 'https://edo-v2.edi-n.com/api/eds/doc?gln=9864065702429&doc_type=orders&doc_number=sdsd334&doc_date=1505497243&recipient=9864065702428&family=edi' -d {json - тело документа} -b 'SID=458a0d38-5b56-4b8e-8998-009a1edd31eb'

Спецификация для расшифровки ключей curl запроса: https://curl.haxx.se/docs/manpage.html

--------------

**JSON-параметры в теле HTTP запроса/ответа**

--------------

**REQUEST**

--------------

В этом методе в json-теле **запроса** передаются поля документа (со `спецификацией документов <https://ссылка на спеку>`__ вы можете ознакомиться в соответствующем разделе).

--------------

**RESPONSE**

--------------

В **ответ** передается "ИД платформы созданного черновика" (длинна 36 символов), например `fb285cdb-31f8-4d59-b89b-77e30e608e12`.

--------------

**Примеры**

--------------

**Пример тела запроса (json):**

.. code:: ruby

   {
	"NUMBER": "6422722fb78c4509b06eac43758e1545",
	"DATE": "2019-02-15",
	"TIME": "00:00",
	"ORDERNUMBER": "6422722fb78c4509b06eac43758e1545",
	"ORDERDATE": "2019-02-15",
	"DELIVERYDATE": "2019-02-30",
	"DELIVERYTIME": "10:00",
	"CAMPAIGNNUMBER": "334455",
	"CURRENCY": "UAH",
	"LIMES": [],
	"HEAD": [
		{
			"BUYER": "4820128010004",
			"SUPPLIER": "9864065702429",
			"DELIVERYPLACE": "4820128019007",
			"INVOICEPARTNER": "4820128010004",
			"SENDER": "4820128010004",
			"RECIPIENT": "9864065702429",
			"POSITION": [
				{
					"POSITIONNUMBER": "1",
					"PRODUCT": "5029053540900",
					"PRODUCTIDBUYER": "527209",
					"DESCRIPTION": "пироженко",
					"PRICE": 510,
					"PRICEWITHVAT": 571.2,
					"VAT": "12.00",
					"AMOUNT": 0,
					"AMOUNTWITHVAT": 0,
					"ORDEREDQUANTITY": 64,
					"ACCEPTEDQUANTITY": 64,
					"PRODUCTTYPE": "1"
				},
				{
					"POSITIONNUMBER": "2",
					"PRODUCT": "5029053540924",
					"PRODUCTIDBUYER": "527215",
					"DESCRIPTION": "мороженко",
					"PRICE": 510,
					"PRICEWITHVAT": 571.2,
					"VAT": "12.00",
					"AMOUNT": 0,
					"AMOUNTWITHVAT": 0,
					"ORDEREDQUANTITY": 32,
					"ACCEPTEDQUANTITY": 32,
					"PRODUCTTYPE": "1"
				},
				...
				{
					"POSITIONNUMBER": "48",
					"PRODUCT": "5029053543987",
					"PRODUCTIDBUYER": "100307632",
					"DESCRIPTION": "водочка",
					"PRICE": 1751.6,
					"PRICEWITHVAT": 1961.79,
					"VAT": "12.00",
					"AMOUNT": 0,
					"AMOUNTWITHVAT": 0,
					"ORDEREDQUANTITY": 12,
					"ACCEPTEDQUANTITY": 12,
					"PRODUCTTYPE": "1"
				}
			]
		}
	],
	"ACTION": "29"
	}

--------------

**Пример тела ответа (json):**

Возвращаемый текст - ID созданного черновика(36 символов)

.. code:: ruby

    fb285cdb-31f8-4d59-b89b-77e30e608e12






