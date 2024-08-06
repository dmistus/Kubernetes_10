# «Helm» 

### Задание 1

### Подготовить Helm-чарт для приложения 
*Необходимо упаковать приложение в чарт для деплоя в разные окружения.*

*Каждый компонент приложения деплоится отдельным deployment’ом или statefulset’ом.*

*В переменных чарта измените образ приложения для изменения версии.*

### Задание 2

### Запустить две версии в разных неймспейсах 

*Подготовив чарт, необходимо его проверить. Запуститe несколько копий приложения.*

*Одну версию в namespace=app1, вторую версию в том же неймспейсе, третью версию в namespace=app2.*

*Продемонстрируйте результат.*

--------

 Устанавливаем на ноду Helm используя скрипт:
 
 ![](img/1.png)
 
 Создаем собственный helm chart с именем myhelm-grafana: 
 
 ![](img/2.png)

Создадим два файла Values - values_dvl.yaml и values_test.yaml для DEVELOP и TEST окружения.
Допишем в них параметры для запуска Grafana, такие как имя образа, тег, порт. Приложения будут развернуты отдельными Deployment. 

-------------
### Задание 2

Создадим отдельный Namespace с именем app1:

![](img/10.png)

Развернем приложения:

![](img/3.png)

![](img/4.png)


Проверим:

![](img/5.png)

![](img/6.png)

Приложения развернуты с помощью Helm в виде отдельных Deployments.


Развернем еще одну версию приложения в Namespace app2:

![](img/7.png)

![](img/8.png)

![](img/9.png)


Проверим Web-интерфейс приложения: 

![](img/11.png)

![](img/12.png)


Ссылка на манифесты:
https://github.com/dmistus/Kubernetes_10/tree/main/src