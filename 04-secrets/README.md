# secret

Секрет - это объект, который содержит небольшое количество 
конфиденциальных данных, таких как пароль, токен или ключ.

Чтобы использовать секрет, pod должен ссылаться на секрет. 
Секрет может быть использован:

- Как файлы в томе, смонтированном на одном или нескольких 
его контейнерах.
- В качестве переменной среды окружения контейнера.

#### Создание secret из файла 
 `kubectl -n volumes-sample create secret generic my-secret --from-file=user=user.txt --from-file=password=password.txt`
 
#### Подключение к pod
`kubectl -n volumes-sample exec openresty-7cd79cfd94-5zjgl -i -t -- bash`