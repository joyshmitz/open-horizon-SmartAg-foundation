
- Налаштування куленепробивного сховища даних для S-Soil MTEC-02B на сервері в локальній мережі

Необхідні умови:
Апаратне забезпечення:
- Raspberry Pi4 модель B 4GB + оперативна пам'ять
https://thepihut.com/products/raspberry-pi-4-model-b?variant=20064052740158

- Цифровий датчик температури та вологості DHT22 (з 3 дротами Dupont)
https://www.amazon.com/Tangyy-Digital-Temperature-Humidity-Raspberry/dp/B08QHW9TS8/

- Карта пам'яті micro SD на 32+ ГБ
https://www.amazon.com/Samsung-MicroSDHC-Adapter-MB-ME32GA-AM/dp/B06XWN9Q99

- Блок живлення для Raspberry Pi 4
https://www.amazon.com/CanaKit-Raspberry-Power-Supply-USB-C/dp/B07TYQRXTK

Навколишнє середовище:
- Wifi стабільно працює. Під час налаштування підключення до інтернету є обов'язковим.
- Після підключення RPi4 повинен знаходитися в зоні дії сигналу Wifi.

Програмне забезпечення:
- Встановіть віртуальну коробку на комп'ютері, де буде працювати Open Horizon Management Hub

- Встановіть Raspberry Pi imager

Кроки для налаштування:
- Завантажте образ RPi4 з попередньо встановленим програмним забезпеченням - 

- Завантажте OH_SmartAG_Ubuntu_18_04_5_LTS.ova - 

- Вставте SD-карту в хост

- Відкрийте візуалізатор Raspberry Pi
  Виберіть цільовий диск
  Натисніть CTRL+SHIFT+X, налаштуйте ім'я та пароль мережі wifi
  Натисніть WRITE, щоб записати образ малини на SD-карту

  Плата малини:
    Підключіть HDT22 за допомогою дроту даних, VCC та GND, як показано на малюнку нижче
    <зображення тут
  
  Зачекайте, поки образ малини буде записано на SD-карту, вставте SD-карту в малинник
  
  Перевірте, чи працює Raspberry Pi
    - перевірте IP-адресу, виконавши 
      sudo nmap -sn 192.168.1.0/24 | awk '/^Nmap/{ip=$NF}/DC:A6:32/{print ip}'
    - підключаємося по ssh до плати Raspberry Pi:
      ssh pi@<IP-адреса з попереднього кроку>.
      пароль: openhorizon
    - Змініть пароль за замовчуванням:
      passwd
