# Forge.MW - Плагин для управления фракциями и ролевой игры

## Содержание
- [Описание](#описание)
- [Особенности](#особенности)
- [Команды](#команды)
- [Механики](#механики)
- [Конфигурация](#конфигурация)
- [Установка](#установка)

## Описание

Forge.MW - это комплексный плагин для Unturned RocketMod, предназначенный для создания уникального ролевого игрового опыта с фракциями, рангами, системой опыта и многими другими функциями.

Плагин идеально подходит для RP-серверов, обеспечивая администраторов и игроков разнообразными инструментами для построения сообщества и игровой вселенной.

## Особенности

- **Система фракций** с иерархией рангов и различными привилегиями
- **Кастомный HUD** для отображения важной игровой информации
- **Система NLR** (New Life Rule) для правильной ролевой игры
- **Система статистики** игроков
- **Объявления** для фракций и всего сервера
- **База данных MySQL** для хранения прогресса игроков
- **Регистрация персонажей** с уникальными особенностями
- **Система штрафов и наград** для управления опытом игроков

## Команды

### Команда Advertisement
Публикация новостей для всех игроков или членов фракции.

| Команда | Описание | Права |
|---------|----------|-------|
| `/ad global <сообщение> [длительность]` | Опубликовать общую новость | `forge.advertisement.global` |
| `/ad faction <сообщение> [длительность]` | Опубликовать фракционную новость | `forge.advertisement.faction` |
| `/ad cancel` | Отменить текущую новость | `forge.advertisement.cancel` |

* Алиасы: `/ad`, `/news`
* Админ-право: `forge.advertisement.admin` (доступ ко всем подкомандам)

### Команда Faction
Управление фракциями: установка штаба, госпиталя, управление составом.

| Команда | Описание | Права |
|---------|----------|-------|
| `/faction sethq <factionId>` | Установить штаб фракции | `forge.faction.sethq` |
| `/faction sethospital <factionId> <radius>` | Установить госпиталь фракции | `forge.faction.sethospital` |
| `/faction transfer <player> <factionId> [force]` | Перевести игрока во фракцию | `forge.faction.transfer` |
| `/faction fire <player>` | Уволить игрока из фракции | `forge.faction.fire` |
| `/faction setleader <player> <factionId>` | Назначить лидера фракции | `forge.faction.setleader` |
| `/faction setdeputy <player> <factionId>` | Назначить заместителя фракции | `forge.faction.setdeputy` |
| `/faction promote <player>` | Повысить игрока в звании | `forge.faction.promote` |
| `/faction demote <player>` | Понизить игрока в звании | `forge.faction.demote` |
| `/faction addexp <player> <amount>` | Добавить опыт игроку | `forge.faction.addexp` |
| `/faction removeexp <player> <amount>` | Удалить опыт у игрока | `forge.faction.removeexp` |
| `/faction invite <player>` | Пригласить игрока во фракцию | `forge.faction.leader` |
| `/faction accept` | Принять приглашение во фракцию | - |
| `/faction deny` | Отклонить приглашение во фракцию | - |

* Алиасы: `/fac`, `/f`
* Админ-право: `forge.faction.admin` (полный доступ ко всем подкомандам)

### Команда Fine
Выдача штрафа игроку в виде снятия очков опыта для уровня.

| Команда | Описание | Права |
|---------|----------|-------|
| `/fine <player> <amount> [причина]` | Оштрафовать игрока | `forge.fine.issue` или `forge.fine.admin` |

### Команда HUD
Включает или выключает интерфейс (HUD).

| Команда | Описание | Права |
|---------|----------|-------|
| `/hud` | Переключить видимость интерфейса | `forge.hud` |

* Алиасы: `/interface`, `/ui`

### Команда Reward
Выдача награды игроку в виде очков опыта для уровня.

| Команда | Описание | Права |
|---------|----------|-------|
| `/reward <player> <amount> [причина]` | Наградить игрока | `forge.reward.issue` или `forge.reward.admin` |

### Команда Stats
Просмотр статистики игроков и рейтинга.

| Команда | Описание | Права |
|---------|----------|-------|
| `/stats` | Открыть меню статистики | `forge.stats.view` |

* Алиасы: `/stat`, `/rating`

## Механики

### Система фракций
- Каждая фракция имеет свой штаб и госпиталь
- Возможность настроить иерархию рангов с требованиями опыта
- Фракции могут быть связаны с группами Steam
- Лидеры и заместители могут управлять составом фракции
- Каждая фракция имеет свою систему рангов и зарплат

### Система рангов
- Игроки получают опыт за активность, убийства, выполнение задач
- При достижении определенного количества опыта ранг автоматически повышается
- Каждый ранг имеет свои привилегии и зарплату
- VIP-игроки могут получать бонусы к зарплате

### Система NLR (New Life Rule)
- При смерти игрок попадает под ограничения NLR
- Запрет на возвращение к месту смерти в течение определенного времени
- Видимый таймер, показывающий оставшееся время NLR
- Возрождение происходит в госпитале фракции с ограничением передвижения

### Система объявлений
- Создание глобальных или фракционных объявлений
- Настраиваемая длительность показа
- Кулдаун между объявлениями
- Только лидеры или их заместители могут публиковать фракционные объявления

### Статистика игроков
- Отслеживание убийств, смертей, K/D соотношения
- Учет уничтоженных транспортных средств
- Система наград и штрафов
- Таблица лидеров для соревновательности

### Регистрация персонажа
- Двухэтапная система регистрации (личные данные, выбор фракции)
- Проверка и валидация всех вводимых данных
- Формирование уникального игрового имени
- Автоматическое определение позиций в общей статистике

## Конфигурация

Плагин использует XML-конфигурацию с широкими возможностями настройки:

```xml
<ConnectionString>server=127.0.0.1;port=3306;uid=root;pwd=12345;database=test</ConnectionString>
<ServerCode>SteamID</ServerCode>
<Password>ServerPassword</Password>
<AdminPermissionGroups>
  <string>admin</string>
  <string>moderator</string>
</AdminPermissionGroups>

<!-- UI настройки -->
<SignupEffectGuid>UI GUID</SignupEffectGuid>
<SignupEffectID>65535</SignupEffectID>
<SignupEffectKey>-32768</SignupEffectKey>

<!-- ... другие UI настройки ... -->

<!-- Настройки объявлений -->
<MaxAdvertisementLength>150</MaxAdvertisementLength>
<DefaultAdvertisementDuration>30</DefaultAdvertisementDuration>
<AdvertisementCooldown>10</AdvertisementCooldown>

<!-- Настройки фракций -->
<Factions>
  <Faction Id="1">
    <Name>FactionOne</Name>
    <Description>Описание фракции 1</Description>
    <PermissionGroups>
      <Group>default1</Group>
      <Group>default2</Group>
    </PermissionGroups>
    <SteamGroup>0</SteamGroup>
    <JoinSteamGroup>true</JoinSteamGroup>
    <FactionLocation>
      <x>0</x><y>0</y><z>0</z>
    </FactionLocation>
    <HospitalLocation>
      <x>0</x><y>0</y><z>0</z>
    </HospitalLocation>
    <HospitalRadius>50</HospitalRadius>
    <Ranks>
      <Rank Order="1">
        <PermissionGroup>group1</PermissionGroup>
        <RequiredPoints>100</RequiredPoints>
        <ExperienceSalary>50</ExperienceSalary>
      </Rank>
      <Rank Order="2">
        <PermissionGroup>group2</PermissionGroup>
        <RequiredPoints>200</RequiredPoints>
        <ExperienceSalary>100</ExperienceSalary>
      </Rank>
    </Ranks>
    <MaxMembers>50</MaxMembers>
  </Faction>
  <!-- ... другие фракции ... -->
</Factions>

<!-- Игровые настройки -->
<KillRewardPoints>10</KillRewardPoints>
<TeamKillPenaltyPoints>5</TeamKillPenaltyPoints>
<TimeExperienceInterval>60</TimeExperienceInterval>
<TimeRewardPoints>15</TimeRewardPoints>
<TimeExperienceReward>20</TimeExperienceReward>
<NLRCooldownTime>240</NLRCooldownTime>

<!-- Награды за уничтожение транспорта -->
<VehicleRewards>
  <VehicleReward Id="1">
    <PointReward>15</PointReward>
    <ExperienceReward>30</ExperienceReward>
  </VehicleReward>
  <!-- ... другие награды ... -->
</VehicleRewards>

<!-- VIP бонусы -->
<ExperienceBonuses>
  <ExperienceBonus Permission="vip.bronze">
    <BonusPercent>10</BonusPercent>
  </ExperienceBonus>
  <!-- ... другие бонусы ... -->
</ExperienceBonuses>
```

## Установка

1. Загрузите файлы плагина в папку `/Plugins/` вашего сервера Unturned
2. Настройте файл конфигурации, особенно параметры подключения к базе данных
3. Создайте базу данных MySQL согласно схеме (таблица `player_data`)
4. Запустите сервер и настройте координаты фракций и госпиталей
5. Установите нужные разрешения для персонала сервера

---

### Примечания

- Плагин требует MySQL 8.0 или выше
- Рекомендуется настраивать фракции перед запуском сервера
- При изменении конфигурации может потребоваться перезапуск сервера
