# BLACK-BUG
* * *
##### Team members:   

1. Telefus Ilya (Product Owner)
2. Zgurovskiy Yaroslav (ScrumMaster)
3. Svynarchuk Maksim (Team Lead)
4. Scherbina Vadim (QA)
5. Horzhyi Igor
6. Poyda Andrian
7. Schupacovskyi Yehor

![TeamLogo](https://github.com/Valzavator/Black-Bug/blob/master/pictures/logo000.png)

# 3D Scanner
* * *
### Project description  


* * *
Рік випуску: 2017<br/>
Версія: 1.0.0<br/>
Розробник: BLACK-BUG<br/>
Платформа: Ubuntu<br/>
<br/>
<h4>Принцип роботи</h4>
Даний сканер створює 3D зображення з об'єктів, що підходять за габаритами до корпусу. Він має лазер, який будує проекцію у вигляді лінії. За допомогою нього, формується 3D об'єкт у програмі FabScan. Це програмне забезпечення за допомгою вихідних сигналів керує мотором і лазером, а також оброблює зображення отримане за допомогою камери. Об'єкт для сканування розміщується на платформі, і при її повороті лазер проектується на цей об’єкт. Після цього веб-камера робить знімки об'єкта і з лінії - проекції лазера на об'єкті, повертає просторові координати всіх світлих 3D точок з картинки, а потім створює з них повноціне 3D зображення, яке пізніше оброблюється в програмі MeshLab.


<h4>Апаратна частина:</h4>
1) Степер мотор (Nema 17);<br/>
2) Драйвер для мотора (L298N);<br/>
3) Лазер (Redline);<br/>
4) Плата (Arduino UNO);<br/>
5) Веб-камера (Logitech C270);<br/>
6) ДВП для корпусу(детальні креслення на зображенні нижче);<br/>
![Frame Scheme](https://github.com/Valzavator/Black-Bug/blob/master/pictures/housingScheme.jpeg)

![Components](https://github.com/Valzavator/Black-Bug/blob/master/pictures/4.jpg)

<h4>Підключення мотора до Arduino UNO</h4>

* [Steper motor](http://arduino-diy.com/arduino-drayver-shagovogo-dvigatelya-i-dvigatelya-postoyannogo-toka-L298N)

 Для підключення Степер мотора необхідно: <br />
  1) Синій провід мотора з'єднати з гніздом (OUT 1) на драйвері; <br />
  2) Червоний провід мотора з'єднати з гніздом (OUT 2) на драйвері; <br />
  3) Чорний провід мотора з'єднати з гніздом (OUT 3) на драйвері; <br />
  4) Зелений провід мотора з'єднати з гніздом (OUT 3) на драйвері; <br />
  (При інших кольорах потрібно підлючити дроти до відповідних виходів зі збереженням полярності.
   За неправильного підключення мотор просто не зможе правильно рухатися)
 Для підключення драйвера до плати Arduino UNO потрібно:<br />
 
  1) Пін (IN1) на драйвері з піном (8)(Digital) на платі Arduino UNO;<br />
  2) Пін (IN2) на драйвері з піном (9)(Digital) на платі Arduino UNO;<br />
  3) Пін (IN3) на драйвері з піном (10)(Digital) на платі Arduino UNO;<br />
  4) Пін (IN4) на драйвері з піном (11)(Digital) на платі Arduino UNO;<br />
  5) Гніздо (+5V) на драйвері з піном (5V)(Power) на платі Arduino UNO;<br />
  6) Гніздо (+12V) на драйвері з піном (Vin)(Power) на платі Arduino UNO;<br />
  7) Гніздо (GND) на драйвері з піном (GND)(Digital) на платі Arduino UNO;<br />
 ![Steper motor](https://github.com/Valzavator/Black-Bug/blob/master/pictures/5.jpg)
 <h4>Підключення лазера до Arduino UNO</h4>
 
 1) З'єднати червоний провід лазера з піном (A4)(Analog) на платі Arduino UNO;
 2) З'єднати чорний провід лазера з піном (GND)(Power) на платі Arduino UNO;
 
 <h4>Завантаження коду на плату Arduino Uno</h4>
 Для завантаження коду на плату необхідно завантажити Arduino IDE за <a href="https://www.arduino.cc/en/main/software">посиланням</a>. 
 Після встановлення програми, підключіть плату до комп'ютера за допомогою USB кабеля.
 Натисність кнопку [Upload] або (ctrl + U) - цим програма завантажиться до плати. 
 
 <h4>Встановлення і налаштування програми Fabscan</h4>
  1) Потрібно скачати образ операційної системи із встановленим Fabscan з <a href="https://mega.co.nz/#!PBpkyaLJ!HI7zpQlAtdMfsEZTHtIGOVrEu5V4HfJIRtR4oGGSgOU">сайту</a>; <br/> 
  2) Потрібно скачати програму Rufus, щоб записати образ системи на флешку або будь-який інший носій, або запустити операційну систему на віртуальній машині;<br/> 
  3) Підключити камеру і Arduino Uno до комп'ютера;<br/> 
  4) Після встановлення потрібно запустити програму Fabscan; <br/> 
  5) У Fabscan натиснути (Camera) і обрати веб-камеру, потім - (SerialPort) і обрати порт;<br/> 
  6) У налаштуваннях обрати Detect laser (перед цим впевнитися, що лазер проходить по центру платформи) і вибрати Fetch frame, налаштувати камеру так, щоб центр платформи проходив по вертикальній жовтій лінії, горизонтальна жовта лінія збігалася з нижнім краєм платформи, а синя - з верхнім краєм;<br/>
  
![Camera](https://github.com/Valzavator/Black-Bug/blob/master/pictures/7DrBMTKedAM.jpg)

![Camera](https://github.com/Valzavator/Black-Bug/blob/master/pictures/7D1fuSHXWdI.jpg)
 
 <h4>Створення 3D моделі в Fabscan</h4>
  1) Нажимаємо Start Scan; <br/> 
  2) Чекаємо доки закінчиться сканування; <br/> 
  3) Зберігаємо 3D зображення; <br/> 
  4) Можемо редактувати його в MeshLab;<br/> 
  
![Fabscan](https://github.com/Valzavator/Black-Bug/blob/master/pictures/Screenshot%20from%202017-05-16%2018_24_02.png)
![Fabscan](https://github.com/Valzavator/Black-Bug/blob/master/pictures/Screenshot%20from%202017-05-16%2018_24_17.png)
=======
## Artifacts:   
* [Trello](https://trello.com/b/F3zNZruQ)
* [Product presentation](http://bit.ly/2lVrU3Q)
* [Documentation](http://bit.ly/2kQ0Qha)
* [Backlog](http://bit.ly/2nkHjvf)
* [Product Promo](https://vimeo.com/217564097)

***
### First Sprint:
 1. [Meeting results](https://docs.google.com/document/d/1kmjobeilXp_ZA3lZIO_0rtM-2dQugZglF6AtuJD-hkA/edit)
 2. [Burndown chart](https://docs.google.com/spreadsheets/d/1LUHoXHVKs5BOQdXvgvltlPh0r4Mgdk2N_VevaNBWwcw/edit#gid=0)
 3. [Demonstration](https://docs.google.com/presentation/d/1RCCShzS-B44vs8E8ptXKodee4wYFuRrP4_AFhzkOGIM/edit#slide=id.p)
 4. [Retrospective](https://docs.google.com/spreadsheets/d/12M1vhFPr1G7U9iy_pcF-Dk78S6Zlp-XNKGRcF35NmX0/edit#gid=0)
***
### Second Sprint:
 1. [Meeting results](https://docs.google.com/document/d/1M6DtZRIyx79GnB-XEwr8rDi_GVmutUE3aYN6NCFEzQU/edit)
 2. [Burndown chart](https://docs.google.com/spreadsheets/d/1ttTtAEPC3I_B0nDH0Pmi0iFZeREc9R0mYm4dI4_D3n8/edit#gid=0)
 3. [Demonstration](https://docs.google.com/presentation/d/1104nvUqWnwmXt8XBXt5iOy6z2K5ebzEyvRYoFUYVLnY/edit?usp=sharing)
 4. [Retrospective](https://docs.google.com/spreadsheets/d/1cNZexZf32fRIZeDvcfuvelYbxX21ZWc3OF92iE9uEN0/edit?usp=sharing)
 
 При виникненні непередбачуваних труднощів, будь ласка, напишіть scrum-майстеру команди BLACK BUG:

vk: <a href="https://vk.com/id146075988">Ярослав Згуровський</a><br/> 

<b>mail</b>: zgurovskiyyarik@gmail.com <br/>
