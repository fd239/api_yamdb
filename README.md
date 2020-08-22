# Yandex API YAMDB

Yandex training project. A django web-app that stores titles, genres and reviews. REST API allow to create, delete and patch users, titles, genres etc. Also supports REST API request for registration with email confirmation

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

Project depends from .env file in root folder. File .env must contain MESSAGE_THEME (str) and  os.getenv('MESSAGE_SENDER') (str) for email confirmation code send properties

```
MESSAGE_THEME = os.getenv('MESSAGE_THEME')
MESSAGE_SENDER = os.getenv('MESSAGE_SENDER')
```

### Installing

```
pip install -r requirements.txt
```

## Running the tests

Project covered with Pytest tests

### Break down into end to end tests

```
pytest
```
It's learning project so test are aimed at checking the fulfillment of a test task

```
  @pytest.mark.django_db(transaction=True)
    def test_03_users_me_not_auth(self, client):
        response = client.get(f'/api/v1/users/me/')

        assert response.status_code != 404, \
            'Страница `/api/v1/users/me/` не найдена, проверьте этот адрес в *urls.py*'

        assert response.status_code == 401, \
            'Проверьте, что при GET запросе `/api/v1/users/me/` без токена авторизации возвращается статус 401'
```

## Built With

* [Django](https://docs.djangoproject.com/en/3.1/) - Django web-framework
* [Yandex Praktikum](https://praktikum.yandex.ru/) - Test tasks and all test in project

## Authors

* **Yandex Praktikum** - *Test task and tests cover* - [yandex-praktikum](https://github.com/yandex-praktikum)
* **Dmitriy Frolov** - *Connection and interaction with Yandex API and Telegram API* - [fd239](https://github.com/fd239)
