Задание 1
Напишите небольшое веб-приложение, используя готовый фреймворк (web.py, Sinatra, …). В этом приложении будет один эндпойнт, который принимает на вход имя файла и подпись.


http://localhost:9000/test?file=foo&signature=46b4ec586117154dacd49d664e5d63fdc88efb51


Сервер при получении подобного запроса будет брать HMAC (функцию HMAC реализуйте самостоятельно) от файла foo и сверять полученное значение со значением signature. Если значения совпадут, то сервер покажет файл, иначе сервер вернет ошибку.

Теперь напишите функцию insecure_compare, которая побайтово сравнивает строки и реализует “ранний выход” (т.е. возвращает False на первой паре не совпавших байт). В цикле insecure_compare добавьте искусственную задержку в 50 мс (например, функцией time.sleep(0.05) в Python).

Для проверки подписи используйте insecure_compare вместо обычной функции сравнения.

Используя факт задержек и раннего выхода, напишите программу, которая будет подбирать валидную подпись для любого файла (без знания ключа!).

В реальном мире подобные уязвимости тяжело эксплуатировать из-за задержек в сети. Однако это хороший пример атаки по сторонним каналам и похожие уязвимости время от времени встречаются в CTF-ах. Например, в 50m-ctf (https://ajxchapman.github.io/security/2019/03/26/h1-702-ctf-2019.html) от HackerOne была очень похожая уязвимость.

http://cryptopals.com/sets/4/challenges/31

Задание 2
Найдите реализацию SHA-1 на вашем языке программирования (например, можно использовать https://github.com/ajalt/python-sha1 для Python). Примечание: это задание является подготовкой к атаке Hash Length Extension, поэтому нужна именно чистая реализация SHA-1, а не библиотечная.

Напишите функцию, которая будет реализовывать MAC вида SHA1(key || message), где || - конкатенация.

Убедитесь, что вы не можете подделать сообщение, не изменив при этом MAC.

http://cryptopals.com/sets/4/challenges/28
