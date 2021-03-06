Безопасный режим и возврат к заводским настройкам
=================================================

Если что-то пошло не так с вашим pyboard - не паникуйте! Сломать pyboard с помощью программирования практически невозможно.

В первую очередь попробуйте войти в безопасный режим: при этом временно пропускается выполнение ``boot.py`` и ``main.py``, используя базовые настройки USB.

Если у вас возникли проблемы с файловой системой - вы можете сделать возврат к заводским настройкам, который восстановит файловую системы в исходное состояние.

Безопасный режим
----------------

Чтобы войти в безопасный режим, выполните следующее:

1. Подключите pyboard по USB.
2. Нажмите и удерживайте кнопку USR.
3. Удерживая USR, нажмите и отпустите RST.
4. Светодиоды начнут поочереди переключаться между режимами: зелёный, оранжевый, зелёный+оранжевый.
5. В тот момент когда будет гореть *только оранжевый светодиод* - отпустите USR.
6. Оранжевый светодиод должен быстро помигать 4 раза и выключиться.
7. Теперь вы в безопасном режиме.

В безопасном режиме файлы ``boot.py`` и ``main.py`` не выполняются и, значит, pyboard загружается с настройками по умолчанию. Это означает, что вы теперь имеете доступ к файловой системе (USB диск должен появиться) и можете редактировать ``boot.py`` и ``main.py`` чтобы устранить любые неполадки.

Вход в безопасный режим является временным и не влечёт никаких изменений в файлах на pyboard.

Возврат файловой системы к заводским настройкам
-----------------------------------------------

Если ваша файловая система будет повреждена (к примеру вы забудите извречь/размонтировать микроконтроллер) или у вас есть код в ``boot.py`` или ``main.py``, который вы не можете отключить - вы всегда можете сбросить файловую систему.

Сброс файловой системы удаляет все файлы во внутренней памяти pyboard (не SD карты), а также восстанавливает файлы ``boot.py``, ``main.py``, ``README.txt`` и ``pybcdc.inf`` обратно к их базовому состоянию.

Чтобы сделать возврат к заводским настройкам, вы должны повторить процедуру входа в безопасный режим, но отпустить кнопку USR в тот момент когда будут гореть зелёный+оранжевый:

1. Подключите pyboard по USB.
2. Нажмите и удерживайте кнопку USR.
3. Удерживая USR, нажмите и отпустите RST.
4. Светодиоды начнут поочереди переключаться между режимами: зелёный, оранжевый, зелёный+оранжевый.
5. В тот момент когда будут гореть *оба светодиода (зелёный и оранжевый)* - отпустите USR.
6. Зелёный и оранжевый светодиоды должны быстро помигать 4 раза.
7. Красный светодиод включится (теперь горят 3 светодиода: красный, зелёный и оранжевый).
8. Сейчас pyboard сбрасывает файловую систему (это займёт несколько секунд).
9. Все светодиоды выключатся.
10. Теперь ваша файловая система в её первозданном виде.
11. Нажмите и отпустите RST для запуска.