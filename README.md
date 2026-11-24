# Иванова Елизавета, ФИТ-1-2025. П04. Деплой веб-сервера с помощью Ansible

## 1. Создаем вторую виртуальную машину с помощью Клонирования

Настройка общей сети и проброс портов 

<img width="886" height="256" alt="image" src="https://github.com/user-attachments/assets/04939e34-3673-4a6e-a6cf-95ea271a948c" />

Настраиваем статические ip адреса машин: bubunta - 10.0.2.15, bubunta2 - 10.0.2.16

## 2.Создаем пользователя и настраиваем SSH на bubunta2

Создаем пользователя runner c паролем 1234 

<img width="503" height="76" alt="image" src="https://github.com/user-attachments/assets/4313c25b-3955-4c01-b04f-b8e0d4df12ed" />

Добавляем строку в /etc/sudoers
```
runner ALL=(ALL) NOPASSWD:ALL 
```

Создаем SSH-ключ в bubunta c помощью команды ssh-keygen 

Копируем ключ на bubunta2 пользователю runner 

<img width="936" height="202" alt="image" src="https://github.com/user-attachments/assets/e1f6549f-46e5-44b4-846e-5ebd21b8234d" />

Заходим на пользователя runner без пароля 

<img width="820" height="313" alt="image" src="https://github.com/user-attachments/assets/ca10f37e-0fd4-45ec-988f-1d4661f01e73" />

## 3. Установка Ansible и написание файлов конфигурации на bubunta

Устанавливаем ansible на bubunta
```
sudo apt install ansible
```
Подготавливаем плейбук и инвентарь 

<img width="804" height="78" alt="image" src="https://github.com/user-attachments/assets/0e3042d6-7c91-4090-aaf1-1f5133f14ff9" />

---

invertory.ini

<img width="463" height="74" alt="image" src="https://github.com/user-attachments/assets/d1b1627f-7f60-447b-9453-a35875c53c7d" />

---

index.html 

<img width="474" height="131" alt="image" src="https://github.com/user-attachments/assets/05086a4e-eabc-4dee-837f-b01259c1e462" />

---

playbook.yml

<img width="624" height="407" alt="image" src="https://github.com/user-attachments/assets/5dc19697-4bcd-4af1-91ba-f509cf1502e2" />

## 4. Запуск и проверка

<img width="1100" height="345" alt="image" src="https://github.com/user-attachments/assets/0cd0f29e-8361-4119-8e89-485c41e296ec" />

Проверяем через браузер 

<img width="687" height="177" alt="image" src="https://github.com/user-attachments/assets/2c02e4ed-18f6-49c0-ab49-0e5b30eef01b" />

