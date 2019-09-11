# tamtam_api_lite
Попытка создать набор простых инструментов для написания ботов на базе API мессенджера TamTam. Набор содержит базовый функционал взаимодействия бота с пользователями и предназначен для начинающих программистов. Синтаксис комманд позволяет легко их модифицировать или создавать на их базе новые комманды используя официальную документацию https://dev.tamtam.chat/ .

Примеры реализации ботов с использованем библиотеки:   

https://github.com/registriren/filelink

https://github.com/registriren/yatranslate
  

Библиотека находится в стадии разработки, поэтому возможны изменения синтаксиса, которые приведут к неработоспособности вашего кода, проверяйте перед применением изменений на своей системе.

Чат для обсуждения вопросов, связанных с работой библиотеки https://tt.me/botapitamtam

Принцип взаимодействия с библиотекой:
- 
1. Методы, которые начинаются с get_ получают события, произошедшие с ботом (написанные или пересланные сообщения, результат нажатия кнопок, вложения и т.д.).
2. Методы, которые начинаются с send_ формируют события в боте (отправляют сообщения, генерируют кнопки и т.д.).
3. В основном цикле Вашей программы осуществляем запрос (long polling), происходящих с ботом событий, методом get_updates. Результат помещаем в переменную ( например update = get_updates() ).
4. Результат работы сформированных вами событий так же можно поместить в переменную (например update = send_message(parametry) ).
4. Для получения "тела" события, которое необходимо обработать, передаем переменную update выбранному методу get_ ( например get_text(update) ), работаем с результатом. 
5. Если запрошенное событие не произошло в ответ получим None.

Описание методов... смотрите в основном коде..
