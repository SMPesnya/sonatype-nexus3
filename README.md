# Структура проекта
├── docker-compose.yml - yaml файл для docker compose<br/>
├── LICENSE            - лицензия LGPL<br/>
└── README.md          - этот файл <br/>

# Как установить и запустить xwiki
## Создание директорий для разделов в контейнерах xwiki и xwiki-postgres  
  ```bash
     sudo mkdir -p /home/docker/nexus3/data
     sudo mkdir -p /home/docker/nexus3/preferences
     sudo chmod 775 -R /home/docker
     sudo chown root:docker -R /home/docker
  ```
> Если тебе не подходит текущие пути для хранения разделов замени их на что-то другое в разделе volumes:
> Или добавь volumes, например для nexus-data
  ```yaml
     volumes:
      - nexus-data:/nexus-data
  ```	
> Пример для preferences 
  ```yaml
     volumes:
      - nexus-preferences:/preferences
  ```	
> В конце файла добавь
  ```yaml
    volumes:
     - nexus-data 
     - nexus-preferences 
  ```
## Скачивание образов и запуск контейнеров 
  ```bash
     docker-compose up -d # скачает образы, запустит контейнеры с нужными настройками
  ```
## Запуск уже существующих контейнеров
  ```bash
     docker-compose start -d # запустит уже существующие контейнеры 
  ```
## Остановка контейнера
  ```bash
     docker-compose stop # остановит запущенные контейнеры
  ```
## Остановка и удаление
  ```bash
     docker-compose down # остановит контейнеры и удалит их, а так-же их образы 
  ```
