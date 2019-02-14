SOAP API
#########

---------

.. contents:: Содержание:

---------

WSDL схема для работы с FTPEX по SOAP: https://soap.edi-n.com/soap/service.wsdl

Получение списка доступных файлов (getList)
==============================================

*Сигнатура* (параметры которые нужно передать): логин и MD5 пароля (те данные, которые были выданы пользователю при подключении к платформе электронного документооборота)(MD5 генератор http://www.danstools.com/md5-hash-generator/).

*В ответ* получаем список имен файлов, которые на данный момент доступны пользователю.

**Пример ответа**:

:: 

 <result>
            <errorCode>0</errorCode>
            <list>status_20150924144604_4679904.xml</list>
            <list>status_20150924144604_7259532.xml</list>
            <list>status_20150924144604_4784911.xml</list>
    ...
    ...
    <list>status_20151005123023_686803070.xml</list>
            <list>order_20151005132435_707890630.xml</list>
  </result>

**Возможные ошибки**:

- errorCode 1 - ошибка при авторизации,
- errorCode 2 - другая ошибка

"Массовое" получение документов (нескольких искомых документов) (getDocuments)
==============================================

*Сигнатура* (параметры которые нужно передать): логин, MD5 пароля и конкретные имена файлов (имена файлов возвращает getList)
*Что возвращает*: код ответа сервера (0 - успешная обработка), а также закодированный в base64 zip архив с запрашиваемыми файлами.

**Пример запроса**:

::

      <soap:getDocumentsRequest>
         <!--Optional:-->
         <user>
            <!--Optional:-->
            <login>login</login>
            <!--Optional:-->
            <pass>parol</pass>
         </user>
         <!--Zero or more repetitions:-->
         <fileName>hello.xml</fileName>
        <fileName>musician.xml</fileName>
      </soap:getDocumentsRequest>

**Пример ответа**:

::

         <result>
            <errorCode>0</errorCode>
          <content>UEsDBBQACAgIAD...AAAA</content>
         </result>

**Возможные ошибки**:

- errorCode 1 - ошибка получения документов (значение ошибки возвращается в <errorMessage/>)

Получение конкретного файла (getDoc)
==============================================

*Сигнатура* (параметры которые нужно передать): логин, MD5 пароля и конкретное имя файла (имена файлов возвращает getList)
*В ответ* получаем конкретный файл в виде BASE-64 строки.

**Пример ответа**:

:: 

  <result>
            <errorCode>0</errorCode>
            <content>PFN0YXR1cz4KI...4KPC9TdGF0dXM+</content>
  </result>

Содержимое поля <content> переводится в XML представление путем расшифровки BASE-64 (в итоге получается тело XML файла).

**Возможные ошибки**:

- errorCode 1 - ошибка при получении документа.

Передача конкретного файла (sendDoc)
==============================================

*Сигнатура* (параметры которые нужно передать) : логин, MD5 пароля, конкретное имя файла и тело файла в виде BASE-64 строки
*В ответ* получаем код ответа сервера (0 - успешная передача).

**Пример ответа**:

:: 

 <result>
            <errorCode>0</errorCode>
 </result>

**Возможные ошибки**:

- errorCode 3 - ошибка при отправке документа

Архивирование документа (удаление конкретного файла с сервера) (archiveDoc)
==============================================

*Сигнатура* (параметры которые нужно передать) : логин, MD5 пароля и конкретное имя файла (имена файлов возвращает getList)
*Что возвращает*: код ответа сервера (0 - успешная обработка).

**Пример ответа**:

:: 

 <result>
            <errorCode>0</errorCode>
 </result>

**Возможные ошибки**:

- errorCode 4 - ошибка при архивации документа

"Массовое" архивирование документов (удаление файлов с сервера) (archiveDocuments)
==============================================

*Сигнатура* (параметры которые нужно передать): логин, MD5 пароля и конкретное имя файла (имена файлов возвращает getList)
*Что возвращает*: код ответа сервера (0 - успешная обработка).

**Пример запроса**:

:: 

      <soap:archiveDocumentsRequest>
         <!--Optional:-->
         <user>
            <!--Optional:-->
            <login>login</login>
            <!--Optional:-->
            <pass>parol</pass>
         </user>
         <!--Zero or more repetitions:-->
             <fileName>hello.xml</fileName>
           <fileName>musician.xml</fileName>
      </soap:archiveDocumentsRequest>

**Пример ответа**:

:: 

 <result>
            <errorCode>0</errorCode>
 </result>

**Возможные ошибки**:

- errorCode 4 - ошибка при архивации документа (значение ошибки возвращается в <errorMessage/>)

Дополнение
==============================================

Полные запросы и ответы сервера по каждому запросу (после клика начнется скачиввние):

:download:`sendDoc_response2.xml<SOAP_API_request_response/sendDoc_response2.xml>`

:download:`sendDoc_request2.xml<SOAP_API_request_response/sendDoc_request2.xml>`

:download:`getList_response2.xml<SOAP_API_request_response/getList_response2.xml>`

:download:`getList_request2.xml<SOAP_API_request_response/getList_request2.xml>`

:download:`getDocumentsResponse2.xml<SOAP_API_request_response/getDocumentsResponse2.xml>`

:download:`getDocumentsRequest2.xml<SOAP_API_request_response/getDocumentsRequest2.xml>`

:download:`getDoc_response2.xml<SOAP_API_request_response/getDoc_response2.xml>`

:download:`getDoc_request2.xml<SOAP_API_request_response/getDoc_request2.xml>`

:download:`archiveDocumentsResponse2.xml<SOAP_API_request_response/archiveDocumentsResponse2.xml>`

:download:`archiveDocumentsRequest2.xml<SOAP_API_request_response/archiveDocumentsRequest2.xml>`

:download:`archiveDoc_response2.xml<SOAP_API_request_response/archiveDoc_response2.xml>`

:download:`archiveDoc_request2.xml<SOAP_API_request_response/archiveDoc_request2.xml>`
