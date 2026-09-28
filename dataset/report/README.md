# Датасет github_ip_security_scan

Результаты аудита безопасности в рамках практической работы №1 «Разработка
безопасного ПО»: развертывание Git, загрузка проекта на GitHub, получение
IP-диапазонов через GitHub Meta API и их анализ (Nmap, Masscan, Nikto).

## Структура
dataset/
├── data/
│   └── scan_findings.csv           # сводная таблица: 13 находок
├── raw/
│   ├── github_ips.txt              # CIDR-диапазоны из GitHub Meta API
│   ├── nmap_result.xml/.txt        # Nmap -sV -sC 127.0.0.1
│   ├── nmap_synscan_fast.xml/.txt  # Nmap -sS --max-rate 100 (scanme)
│   ├── masscan_result.xml          # Masscan --rate 100 (scanme)
│   └── nikto_report.html/.csv      # Nikto (обе цели)
├── meta/
│   └── scan_findings.meta          # метаданные датасета
└── report/
    ├── README.md                   # этот файл
    ├── expert_assessment.md        # экспертная оценка
    └── sources.md                  # источники

## Формат scan_findings.csv
finding_id — номер находки; tool — инструмент; target_ip — IP цели;
port — TCP-порт; severity — Critical/High/Medium/Low; category — класс находки;
description — описание; expert_comment — рекомендация эксперта.

## Юридическая оговорка
Сканирование проводилось только собственных ресурсов и авторизованной
демо-цели scanme.nmap.org с ограничением скорости (≤ 100 pps).
