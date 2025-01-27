---
layout: base
title: "AttaliTech | Expert R-Shiny Consulting"
css:
  - /assets/css/index.css
ext-css:
  - //fonts.googleapis.com/css?family=Roboto:400,700
js:
  - /assets/js/index.js
ext-js:
  - //cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js
---

<div id="header" class="cut1" markdown="1">

<div id="header-inner" markdown="1">

# Фатум (СПб) {#title}

## Аудит и консалтинг {#subtitle}

#### Член СРО ААС [ОРНЗ 12206014536](https://sroaas.ru/firms/12206014536/?tab=tab1) {#sub-subtitle}

<a href="/contact" class="actionbtn">
  <span class="far fa-envelope" aria-hidden="true"></span>
    Свяжитесь с нами
</a>
{: .actionbtn-out :}

</div>
<div id="particles-js"></div>
</div>
<div id="main-sections">

<div id="services-out" class="page-section cut1">
  <div id="services">
    <div class="section-title">Что мы предлагаем</div>
    <div id="services-list">
        <div class="service">
        <img class="service-img" alt="Service image" src="/assets/img/scale-flexiple/Complex dashboard.png" />
        <div class="service-text">Обязательный и инициативный аудит</div>
        </div>
        <div class="service">
        <img class="service-img" alt="Service image" src="/assets/img/scale-flexiple/Successful completion of project.png" />
        <div class="service-text">Консалтинг по вопросам бухучета и налогообложения</div>
        </div>
        <div id="services-break"></div>
        <div class="service">
        <img class="service-img" alt="Service image" src="/assets/img/scale-flexiple/Bug tracking.png" />
        <div class="service-text">Ведение налоговых споров в судах</div>
        </div>
        <div class="service">
        <img class="service-img" alt="Service image" src="/assets/img/scale-flexiple/Work risk-free.png" />
        <div class="service-text">Внедрение IT в области бухучета</div>
        </div>
    </div>
    <a href="/contact" class="actionbtn">
      <span class="far fa-envelope" aria-hidden="true"></span>
        Свяжитесь с нами
    </a>
  </div>
</div>

<div class="cut-buffer aboutus-buffer"></div>

<div id="aboutus-out" class="page-section grey-section cut2">
  <div id="aboutus">
    <div class="section-title">Раскрытие информации</div>
    <div id="aboutus-text">
    </div>
<!-- Таблица из файла aboutus.yml -->
    <table class="styled-table">
      <thead>
        <tr>
          <th>Наименование</th>
          <th>Значение</th>
        </tr>
      </thead>
      <tbody>
        {% for row in site.data.aboutus.aboutus %}
          <tr>
            <td class="header-cell">{{ row["заголовок"] }}</td>
            <td class="value-cell">{{ row["значение"] }}</td>
          </tr>
        {% endfor %}
      </tbody>
    </table>
    <!-- Конец таблицы -->
  </div>
</div>

<div class="cut-buffer values-buffer"></div>

<div id="values-out" class="page-section cut2">
  <div id="values">
	  <div class="section-title">Повышение квалификации</div>
    <div id="values-text">
    Мы ежегодно проходим курсы обязательного повышения квалификации аудиторов.
    </div>
    <div id="shinyapps-big">
      {% for value in site.data.values %}
        <div class="shinyapp">   
          {% assign pdf_name = value.img | remove: '.png' | remove: '.jpg' | remove: '.jpeg' | remove: '.gif' | append: '.pdf' %}
          
          {% if pdf_name contains ".pdf" %}
            <a class="applink" href="/assets/img/serts/{{ pdf_name }}" target="_blank">
          {% else %}
            <a class="applink" href="{{ value.url }}">
          {% endif %}
            <img class="appimg" src="/assets/img/serts/{{ value.img }}" />
            <div class="apptitle">{{ value.title }}</div>
            <div class="appdesc">{{ value.description }}</div>
          </a>
        </div>
      {% endfor %}
    </div>
    <a href="/contact" class="actionbtn">
      Свяжитесь с нами
    </a>
  </div>
</div>

<div id="clients-out" class="page-section cut1">
  <div id="clients">
    <div class="section-title">Клиенты</div>
    <div id="clients-subtitle">За период работы фирмы мы приобрели более 30 клиентов.</div>
    <div id="client-logos">
      {% for client in site.data.clients %}
        <a class="client-img" href="{{ client.url }}" title="{{ client.name }}">
          <img alt="{{ client.name }}" src="/assets/img/logos/{{ client.img }}" />
        </a>
      {% endfor %}
    </div>
  </div>
</div>

<div class="cut-buffer"></div>

<div id="aboutme-section-out" class="page-section grey-section cut2">
  <div id="aboutme-section">
    <div class="section-title">Обязательный аудит в 2024 г.</div>
    <!-- Контейнер для графика -->
    <canvas id="monthChart" width="400" height="200"></canvas>
    <!-- Скрипт для построения графика -->
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <script>
      // Загружаем данные из JSON
      const chartData = {
        "chartData": [
          { "month_name": "Январь", "month_number": 1, "count": 31 },
          { "month_name": "Февраль", "month_number": 2, "count": 1000 },
          { "month_name": "Март", "month_number": 3, "count": 17039 },
          { "month_name": "Апрель", "month_number": 4, "count": 5958 },
          { "month_name": "Май", "month_number": 5, "count": 1070 },
          { "month_name": "Июнь", "month_number": 6, "count": 991 },
          { "month_name": "Июль", "month_number": 7, "count": 952 },
          { "month_name": "Август", "month_number": 8, "count": 361 },
          { "month_name": "Сентябрь", "month_number": 9, "count": 312 },
          { "month_name": "Октябрь", "month_number": 10, "count": 298 },
          { "month_name": "Ноябрь", "month_number": 11, "count": 298 },
          { "month_name": "Декабрь", "month_number": 12, "count": 1011 }
        ]
      };
      // Извлекаем данные для графика
      const labels = chartData.chartData.map(item => item.month_name);
      const data = chartData.chartData.map(item => item.count);
      // Конфигурация графика
      const ctx = document.getElementById('monthChart').getContext('2d');
      const monthChart = new Chart(ctx, {
        type: 'bar',
        data: {
          labels: labels,
          datasets: [{
            label: 'Количество проаудированных фирм по данным ГИРБО',
            data: data,
            backgroundColor: 'rgba(75, 192, 192, 0.2)',
            borderColor: 'rgba(75, 192, 192, 1)',
            borderWidth: 1
          }]
        },
        options: {
          responsive: true,
          plugins: {
            legend: {
              position: 'top'
            },
            tooltip: {
              callbacks: {
                label: function(context) {
                  return `${context.label}: ${context.raw}`;
                }
              }
            }
          },
          scales: {
            x: {
              title: {
                display: true,
                text: 'Месяц'
              }
            },
            y: {
              beginAtZero: true,
              title: {
                display: true,
                text: 'Количество'
              }
            }
          }
        }
      });
    </script>
  </div>
</div> 

<div class="cut-buffer portfolio-buffer"></div>

<div id="portfolio-out" class="page-section grey-section">

  <div id="portfolio">
    <div class="section-title">
      Документы
    </div>
    <div id="shinyapps-big">
      {% for app in site.data.portfolio %}
        <div class="shinyapp">   
          {% assign pdf_name = app.img | remove: '.png' | remove: '.jpg' | remove: '.jpeg' | remove: '.gif' | append: '.pdf' %}         
          {% if pdf_name contains ".pdf" %}
            <a class="applink" href="/assets/img/screenshots/{{ pdf_name }}" target="_blank">
          {% else %}
            <a class="applink" href="{{ app.url }}">
          {% endif %}
            <img class="appimg" src="/assets/img/screenshots/{{ app.img }}" />
            <div class="apptitle">{{ app.title }}</div>
            <div class="appdesc">{{ app.description }}</div>
          </a>
        </div>
      {% endfor %}
    </div>
  </div>
</div>

<div id="cta-out" class="page-section">
  <div id="cta">
    <div class="section-title">Аудит и консалтинг в СПб</div><br/>
  </div>
  <a href="/contact" class="actionbtn">
    <span class="far fa-envelope" aria-hidden="true"></span>
    Свяжитесь с нами
  </a>
</div>

</div>

