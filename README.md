# Install-HACS-to-Home-Assistant-2025
Гайд по установке HACS в Home Assistant в 2025 году (Репозиторий скорее для себя заметка, тут пока нету каких то подробностей, я устал😓)

# Добавляем HACS в Home Assistant
Дополнение к:

[Получаем доступ по ssh к серверу Home Assistant на HassOS - У Павла!](https://psenyukov.ru/%d0%bf%d0%be%d0%bb%d1%83%d1%87%d0%b0%d0%b5%d0%bc-%d0%b4%d0%be%d1%81%d1%82%d1%83%d0%bf-%d0%bf%d0%be-ssh-%d0%ba-%d1%81%d0%b5%d1%80%d0%b2%d0%b5%d1%80%d1%83-home-assistant-%d0%bd%d0%b0-hassos/)

[Добавляем HACS в Home Assistant - IO Home](https://io-home.ru/home-assistant/integrations/dobavljaem-hacs-v-home-assistant/)

ВНИМАНИЕ, КОМАНДА ВВОДИТЬСЯ НЕ В ТЕРИМНАЛ СИСТЕМЫ ARMBIAN, В КОТОРУЮ УСТАНОВЛЕН Home Assistant, А ВВОДИМ ЕЕ В ТЕРМИНАЛ САМОГО HOME ASSISTANT!!! ЧЕРЕЗ АДДОН ЭТО ДЕЛАЕТСЯ!


Включаем расширенный режим (нажимаем на значок профиля)

Генерируем ключи RSA для SSH:
В мобаЕкстерн:
Tools -> MobaKeyGen (SSH key generator)

В окошке будет публичный ключ:
```
ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCSPH0v/sZhlXGnkHP9ezA/0xRp60JFHWv9onc9kbmUXhkcN9KwwfexXecDndZkH/xTubfoZUpqXKMHRVeg2fnjytkCNF/xYMrmLuus/ob7YKLE5dA7I4WNpw/0RsSlJz8fvDbv/OHme9PPpX0lpEAMxAQ1kjYN92R2gJAQHX0T9bvHGEO4UKCxl4xDIdHUW9H6vplOiRUjwuLurxuqYx5LLdRpAS9sAM6+8Em5a7sWNIQ2lcJ/5z4BDpU0JOrBfCljxCGIy3Cog+lvxB1l//U2ucMwxuy4W6s8bxBscIxjoo9Fqq5544cxBA1K4Dsv1rB9z4g8HdD66ViCoXkM5Ni/ rsa-key-20250731
```
Но из всего этого текста вот этот кусок является ключом:

```
AAAAB3NzaC1yc2EAAAADAQABAAABAQCSPH0v/sZhlXGnkHP9ezA/0xRp60JFHWv9onc9kbmUXhkcN9KwwfexXecDndZkH/xTubfoZUpqXKMHRVeg2fnjytkCNF/xYMrmLuus/ob7YKLE5dA7I4WNpw/0RsSlJz8fvDbv/OHme9PPpX0lpEAMxAQ1kjYN92R2gJAQHX0T9bvHGEO4UKCxl4xDIdHUW9H6vplOiRUjwuLurxuqYx5LLdRpAS9sAM6+8Em5a7sWNIQ2lcJ/5z4BDpU0JOrBfCljxCGIy3Cog+lvxB1l//U2ucMwxuy4W6s8bxBscIxjoo9Fqq5544cxBA1K4Dsv1rB9z4g8HdD66ViCoXkM5Ni/
```

Ставим аддон в HA:
Terminal & SSH
ИМЕННО ЭТОТ, ПРЯМ ДОСЛОВНО ВБИВАТЬ!
Открываем конфиг плагина и там в ключ авторизации вставляем наш ключ, без лишних приписок!

## Сама установка HACS
Вводим руками это команду в терминал аддона:
```
wget -O - https://get.hacs.xyz | bash -
```

Нажимаем ctrl+R чтобы отчистить кэш браузера и перезапускаем HA.

В интеграциях добавляем HACS и входим через гитхаб.

