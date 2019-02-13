###################
Кофигурация AS2
###################


Mendelson AS2 configuration
==============================================
.. csv-table:: Таблица 1 - Mendelson AS2 configuration
  :file: Tables/Table_1_Mendelson_AS2_configuration.csv
  :widths:  5, 5

Параметры передачи данных
==============================================
.. csv-table:: Таблица 2 - Параметры передачи данных
  :file: Tables/Table_2_Parametry_peredachi_dannyh.csv
  :widths:  5, 5, 5
  
AS2 Сертифицирование
==============================================
.. csv-table:: Таблица 3 - AS2 Сертифицирование
  :file: Tables/Table_3_AS2_Sert.csv
  :widths:  5, 5


**Сертификаты** используются при передаче данных по https, а также для их шифрования (дополнительного в случае передачи по https).

Полная цепочка сертификатов, необходимая для установки связи: **root - intermedia - edin**

:download:`Root сертификат - DigiCert_Global_Root_CA.crt<DigiCert_Global_Root_CA.crt>`
:download:`Сертификат Intermediate CA - Intermediate_CA.crt<Intermediate_CA.crt>`
:download:`Вложенный сертификат EDI-N (Organization Validation) - OV_edi-n.com.crt<OV_edi-n.com.crt>`
