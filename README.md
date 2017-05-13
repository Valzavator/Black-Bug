# BLACK-BUG
* * *
Team members:   

1.Telefus Ilya (Product Owner)   
2.Zgurovskiy Yaroslav (ScrumMaster)   
3.Svynarchuk Maksim (Team Lead)   
4.Scherbina Vadim (QA)   
5.Horzhyi Igor   
6.Poyda Andrian   
7.Schupacovskyi Yehor   

![TeamLogo](https://github.com/Admiral2303/Black-Bug/blob/master/logo000.png)

# 3D Scanner
* * *
Project description  

Artifacts:   
* [Trello](https://trello.com/b/F3zNZruQ)    


* * *
Рік випуску: 2017<br/>
Версія: 1.0.0<br/>
Розробник: BLACK-BUG<br/>
Платформа: Ubuntu<br/>
<br/>

<h4>Підключення мотора до Arduino UNO</h4>

* [Steper motor](http://arduino-diy.com/arduino-drayver-shagovogo-dvigatelya-i-dvigatelya-postoyannogo-toka-L298N)

 Для підключення <h4>Степер мотора</h4> необхідно: <br />
  1) Синій провід мотора з'єднати з гніздом (OUT 1) на драйвері <br />
  2) Червоний провід мотора з'єднати з гніздом (OUT 2) на драйвері <br />
  3) Чорний провід мотора з'єднати з гніздом (OUT 3) на драйвері <br />
  4) Зелений провід мотора з'єднати з гніздом (OUT 3) на драйвері <br />
 
 Для підключення <h4>драйвера</h4> до плати Arduino UNO потрібно:<br />
 1) Пін (IN1) на драйвері з піном (8)(Digital) на платі Arduino UNO
 2) Пін (IN2) на драйвері з піном (9)(Digital) на платі Arduino UNO
 3) Пін (IN3) на драйвері з піном (10)(Digital) на платі Arduino UNO
 4) Пін (IN4) на драйвері з піном (11)(Digital) на платі Arduino UNO
 5) Гніздо (+5V) на драйвері з піном (5V)(Power) на платі Arduino UNO
 6) Гніздо (+12V) на драйвері з піном (Vin)(Power) на платі Arduino UNO
 7) Гніздо (GND) на драйвері з піном (GND)(Digital) на платі Arduino UNO
 
 <h4>Підключення лазера до Arduino UNO</h4>
 
 1) З'єднати червоний провід лазера з піном (A4)(Analog) на платі Arduino UNO
 2) З'єднати чорний провід лазера з піном (GND)(Power) на платі Arduino UNO
 
 <h4>Завантаження коду на плату Arduino Uno</h4>
 Для завантаження коду на плату необхідно завантажити Arduino IDE за посиланням
 Після встановлення програми, підключіть плату до комп'ютера за допомогою USB кабеля.
 Натисність кнопку [Upload] або (ctrl + U) - цим програма завантажиться до плати. 
 
 <h4>Встановлення і налаштування програми Fabscan</h4>
 1) Потрібно скачати образ операційної систеи із встановленим Fabscan з * [сайту](http://hci.rwth-aachen.de/fabscan_software) 
 2) Потрібно скачати програму Rufus щоб записати образ системи на флешку або будь-який інший носій, або запустити операційну систему на віртуалкі
 3) Підключити камеру і Arduino Uno до компютера
 3) Після встановлення потрібно вибрати зліва програму Fabscan 
 4) В Fabscan вибрати (Camera) і вибрати свою камеру, потім вибрати (SerialPort) і вибрати порт
 5) В налаштуваннях нажати Detect laser і вибрати Fetch frame, налаштувати щоб центр платформи проходив по жовтій лінії, а синя  лінія збігалася з краєм платформи  
 
 <h4>Створення 3D моделі в Fabscan</h4>
1) Нажимаємо Start Scan 
2) Чекаємо доки закінчиться сканування 
3) Зберігаємо 3D зображення 
4) Можемо редактувати його в MashLab
