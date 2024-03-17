<div align='center'>
<h1>
  SQL
  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="30px"/>
</h1>
</div>
<div align='center'>
    <img src="https://img.shields.io/badge/Python-%23AFEEEE?style=for-the-badge&logo=Python&logoColor=yellow"/>
   <img src="https://img.shields.io/badge/SQL-%23AFEEEE?style=for-the-badge&logo=SQL&logoColor=yellow"/>
   <img src="https://img.shields.io/badge/ClickHouse%20-%23AFEEEE?style=for-the-badge&logo=ClickHouse&logoColor=%23FFCC01"/>
   <img src="https://img.shields.io/badge/Pandahouse-%23AFEEEE?style=for-the-badge&logo=Pandahouse&logoColor=yellow"/>
</div>

## В данном проекте проанализируем данные образовательных курсов с помощью SQL-запросов в ClickHouse, выгрузив в Python используя библиотеку Pandahouse.

### Определим количество усердных учеников образовательных курсов.
Под усердными учениками мы будем подразумевать учеников, которые хотя бы раз за текущий месяц правильно решили 20 заданий.

![image](https://github.com/KinderDs/SQL/assets/163444205/31f5e779-e414-400c-ac25-d34d9b09ac8d)

### Количество решений заданий в день на образовательной платформе ограничено, чтобы получить доступ к неограниченному количеству заданий в определенной дисциплине, необходимо приобрести подписку. Наша команда провела эксперимент, где был протестирован новый экран оплаты. 

### Для анализа нашего эксперемента рассмотрим метрики тестовой и контрольной группы:

*  ARPU
*  ARPAU
*  CR в покупку
*  СR активного пользователя в покупку
  
  Активным будем считать пользователя, который за все время решил больше 10 задач правильно в любых дисциплинах.
*  CR пользователя из активности по математике в покупку курса по математике
  
  Активным по математики будем считать пользователя, который за все время решил больше 2 и более задач правильно по математике.
*  ARPU считается относительно всех пользователей, попавших в группы.

![image](https://github.com/KinderDs/SQL/assets/163444205/92fd5ef6-8e89-416d-8835-60cab8d4a482)


<details>
  <summary><b> 🛠 &nbsp;&nbsp;Используемые данные:&nbsp;</b></summary>
  <br/> 
<div>
<details>
  <summary><b>&nbsp;&nbsp;default.peas — таблица с данными решенных заданий&nbsp;</b></summary>
  
* st_id — ID ученика

* timest —  Время решения карточки

*  correct —  Правильно ли решена задача?

*  subject —  Дисциплина, в которой находится задание

</details>

<details>
  <summary><b>&nbsp;&nbsp;default.studs —  таблица с принадлежностью к группе эксперимента&nbsp;</b></summary>
  
*  st_id —  ID ученика

*  test_grp —  Метка ученика в данном эксперименте

</details>

<details>
  <summary><b>&nbsp;&nbsp;default.final_project_check —  данные по покупках курса &nbsp;</b></summary>
  
*  st_id —  ID ученика
  
*  sale_time —  Время покупки
   
*  money —  Цена, по которой приобрели данный курс
   
*  subject — Дисциплина
   
</details>
</div>
</details>
