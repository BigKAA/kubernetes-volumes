# configMap

Применяется для создание конфигурационных файлов или любых
других не пустых файлов.

Содержимое configMap хранится в базе etcd. Поэтому не имеет 
смысл использовать его для больших бинарных файлов.

Текстовые данные должны быть в кодировке UTF-8. Если
файл должен быть в другой кодировке, используйте binsryData.

Необходимо сначала создать объект configMap, прежде чем вы 
начнёте его использовать.

#### Создание configMap из файла index.html:

`kubectl create configmap index-html --from-file=index.html --dry-run=client -o yaml | sed '/creationTimestamp/d' > 00-index-html.yaml`

#### Создание configMap, включая в него все файлы в текущей директории:

`kubectl create configmap index-html --from-file=./ --dry-run=client -o yaml | sed '/creationTimestamp/d' > 00-index-html.yaml`

#### Применение configMap
    
`kubectl -n volumes-sample apply -f 00-index-html.yml`
