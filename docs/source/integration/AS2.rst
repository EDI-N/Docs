###################
Кофигурация AS2
###################
Сертификаты используются при передаче данных по https, а также для их шифрования (дополнительного в случае передачи по https).

Полная цепочка сертификатов, необходимая для установки связи: **root - intermedia - edin**

Root сертификат - DigiCert_Global_Root_CA.crt

Сертификат Intermediate CA - Intermediate_CA.crt

Вложенный сертификат EDI-N (Organization Validation) - OV_edi-n.com.crt


Таблица 1 - Mendelson AS2 configuration
==============================================
.. csv-table:: Mendelson AS2 configuration
  :file: Tables/Table_1_Mendelson_AS2_configuration.csv
  :widths:  5, 5
