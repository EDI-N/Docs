*********************************************************************************
Формирование и отправка документа «Подтверждение заказа» (ORDRSP) на платформе
*********************************************************************************
---------

.. contents:: Содержание:
   :depth: 6

---------

Введение
====================================
Данная инструкция описывает порядок формирования и отправки документа «**Подтверждение заказа**» (**ORDRSP**).

Подтверждение заказа
=================================

Чтобы сформировать документа «**Подтверждение заказа**» (**ORDRSP**), перейдите в раздел «**Входящие**», для удобства выберете фильтр по типу документа «**Заказ**» и откройте его.

.. image:: pics_formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web/formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web_01.png
   :align: center


.. image:: pics_formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web/formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web_02.png
   :align: center

В открытой форме, все поля обозначенные красной звёздочкой * **обязательны для заполнения**.

.. image:: pics_formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web/formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web_03.png
   :align: center

1. **Номер** - может совпадать с номером заказа
2. **Дата** - дата подтверждения, автоматически указана текущая дата
3. **Дата заказа** - автоматически переносится из заказа
4. **Подтвержденная дата поставки** - переносится из заказа (если с сетью согласован перенос - измените её)
5. **Действия** - выбирается из следующих: **Будет доставлено, Изменения количества, или Отказано**

Ниже на странице созданного документа находится перечень товарных позиций, которые были заказаны, и их количество:

.. image:: pics_formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web/formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web_04.png
   :align: center

Система автоматически подставляет значение в колонку «**Подтверждено**» аналогичное заказанному, а в колонку «**Действия**» статус «**Будет доставлено**».

Редактирование товарных позиций
================================================

В случае, если вам необходимо изменить количество подтвержденного товара, в колонке «**Действия**», выберете пункт «**Изменение количества**», после этого внесите количество подтверждаемого товара.

.. important:: **Внимание!** Подтвержденное количество товарных позиций не может превышать указанное в заказе!

Если какая-то из позиций отсутствует и поставляться не будет, в колонке «**Действия**», выберете пункт «**Отказано**», значение в колонке «**Количество**» автоматически будет изменено на 0.

.. image:: pics_formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web/formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web_05.png
   :align: center

После внесения всех данных в документе, нажмите кнопку «**Сохранить**», затем «**Отправить**»

.. image:: pics_formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web/formirovanie_otpravka_dokumenta_Podtverzhdenie_zakaza_ORDRSP_na_web_06.png
   :align: center

Отправленный документ автоматически попадает в папку «**Отправленные**» и будет находится в цепочке документов вместе с заказом.

.. include:: kontakti.rst
