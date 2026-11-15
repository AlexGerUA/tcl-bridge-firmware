# TCL Bridge — що нового / What's new

Найновіша версія — згори. Міст перевіряє оновлення раз на добу; встановлення — кнопкою
«Оновити» на вкладці «Мережа» або в Home Assistant.

The newest version is on top. The bridge checks for updates once a day; install with the
"Update" button on the Network tab or in Home Assistant.

---

## 1.1.9 — 2026-11-15

- **Розклад** — нова вкладка між «Пульт» і «Home Assistant». До 10 сценаріїв: «увімкнути на період»
  (дні тижня, час увімкнення й вимкнення, режим, температура, вентилятор — кожне можна лишити «без змін»)
  або «лише вимкнути» в заданий час. Сценарії, що перетинаються, сторінка не дасть зберегти й покаже, з
  яким сценарієм конфлікт. Розклад виконує сам міст — без інтернету й хмари; час береться з інтернету,
  часовий пояс вибирається на вкладці. Між увімкненням і вимкненням кондиціонером можна керувати як завжди.
- У Home Assistant — перемикач «Schedule enabled» (увімкнути чи вимкнути весь розклад разом).
- Вкладка «VPN WireGuard»: кнопка вибору файлу .conf стала помітною й рівною з іншими.

- **Schedule** — a new tab between "Remote" and "Home Assistant". Up to 10 scenarios: "on for a period"
  (weekdays, on and off time, mode, temperature, fan — each can be left "no change") or "off only" at a
  set time. Overlapping scenarios cannot be saved; the page shows which scenario is in the way. The
  bridge runs the schedule itself — no internet or cloud needed; time comes from the internet, the time
  zone is chosen on the tab. Between on and off you can control the AC as usual.
- In Home Assistant — a "Schedule enabled" switch (turn the whole schedule on or off).
- "VPN WireGuard" tab: the .conf file button is now easy to see and lined up with the others.

## 1.1.8 — 2026-11-15

- **Уставка з кроком 0,5 °C** на всіх кондиціонерах (сторінка моста й Home Assistant). Міст тепер
  показує справжню уставку з пів градусом — раніше ці пів градуса (поставлені пультом чи додатком)
  не було видно, а нова команда моста їх не знімала.
- **Режим генератора** для кондиціонерів з протоколом A5: обмеження струму L1–L6 (30–80 %), для роботи
  від генератора чи слабкої мережі. Діє, коли кондиціонер увімкнено.
- **Самоочищення випарника** для кондиціонерів з протоколом A5: кнопка й стан на сторінці та в Home Assistant.
- **Виправлено:** на A5 звіт, у якому кондиціонер повідомляє про роботу обмежувача струму, міг читатися
  не до кінця.
- Детальний журнал змін полів шини — лише з увімкненою діагностикою (Diag).

- **Setpoint in 0.5 °C steps** on all air conditioners (bridge page and Home Assistant). The bridge now
  shows the real setpoint including the half degree — before, a half degree set by the remote or the app
  was not shown and the bridge's next command did not clear it.
- **Generator mode** for A5-protocol air conditioners: current limit L1–L6 (30–80 %) for running on a
  generator or a weak grid. Works while the AC is on.
- **Evaporator self-clean** for A5-protocol air conditioners: button and state on the page and in Home Assistant.
- **Fixed:** on A5, a report announcing the current limiter could be read only partially.
- The detailed log of bus field changes now appears only with diagnostics (Diag) on.

## 1.1.7 — 2026-11-15

- **Кондиціонери з протоколом A5** (наприклад, TCL SaveIn 09ZG11) тепер мають повне керування:
  швидкість вентилятора (авто, 1–6, турбо), жалюзі вгору-вниз і вліво-вправо (гойдання та
  фіксовані положення), ECO, здоровий режим, підсвітка дисплея, звук, режим сну, обігрів +8 °C.
  Стан, зокрема положення жалюзі, читається з кондиціонера.
- **Пульт на сторінці моста показується завжди.** Поки кондиціонер не повідомив стан, кнопки
  неактивні й над ними видно «Зʼєднуюсь із кондиціонером…»; раніше пульт зникав повністю.
- **Виправлено:** на A5 поле «Протокол» могло лишатися порожнім, і сторінка писала «Шукаю
  кондиціонер…» при живому звʼязку.
- Поки протокол не визначено, міст нічого не надсилає кондиціонеру — команда чекає.
- Жалюзі й режим сну більше не надсилають у Home Assistant той самий стан щосекунди.

- **A5-protocol air conditioners** (e.g. TCL SaveIn 09ZG11) now have full control: fan speed (auto,
  1–6, turbo), up-down and left-right louvers (swing and fixed positions), ECO, healthy mode,
  display light, beep, sleep mode, +8 °C heating. The state, louver position included, is read
  from the AC.
- **The remote on the bridge page is always shown.** Until the AC reports its state the
  controls are inactive with "Connecting to the air conditioner…" above them; before, the
  remote disappeared completely.
- **Fixed:** on A5 the "Protocol" field could stay empty and the page said "Searching for the
  AC…" while the link was alive.
- Until the protocol is known the bridge sends nothing to the AC — the command waits.
- Louvers and sleep mode no longer send the same state to Home Assistant every second.

## 1.1.6 — 2026-11-15

- Нові функції: **ECO**, **здоровий режим**, **режим сну** (стандартний, для літніх людей, для
  дітей), **м'який обдув** (лише на охолодженні), **обігрів +8 °C** — на сторінці моста й у
  Home Assistant. Стан читається з кондиціонера, тож правильний і після пульта чи додатку.
- **Виправлено:** кнопка самоочищення випарника тепер справді його запускає.
- **Виправлено:** найнижча швидкість вентилятора — така сама, як у додатку TCL Home.
- **Виправлено:** зміни з пульта (ECO, підсвітка, турбо…) більше не скасовуються наступною
  командою з моста.
- Сторінка пропонує оновлення лише на новішу версію, а не на старішу.

- New: **ECO**, **healthy mode**, **sleep mode** (standard, for elderly, for children),
  **gentle wind** (cooling only), **+8 °C heating** — on the bridge page and in Home Assistant.
  The state is read from the AC, so it stays right after the remote or the app.
- **Fixed:** the evaporator self-clean button now really starts it.
- **Fixed:** the lowest fan speed now matches the TCL Home app.
- **Fixed:** changes made with the remote (ECO, display light, turbo…) are no longer undone by
  the bridge's next command.
- The page offers an update only to a newer version, never an older one.

## 1.1.5 — 2026-11-15

- **Виправлено:** оновлення більше не відкочується на попередню версію, якщо в першу хвилину
  після нього зберегти налаштування VPN, перезавантажити чи скинути міст.
- Кнопка «Restart» у Home Assistant працює так само безпечно, як і на сторінці моста.

- **Fixed:** an update is no longer rolled back to the previous version when VPN settings are
  saved, or the bridge is restarted or reset, during its first minute.
- The "Restart" button in Home Assistant is now as safe as the one on the bridge page.

## 1.1.4 — 2026-11-15

- VPN WireGuard: файл клієнта `.conf` можна завантажити кнопкою «Або виберіть файл .conf» —
  поля заповнюються самі.

- VPN WireGuard: load the client `.conf` file with the "Or choose a .conf file" button — the
  fields fill in by themselves.

## 1.1.3 — 2026-11-14

- На сторінці точки доступу (налаштування Wi-Fi) з'явився рядок «Перезавантажити / Reboot».

- The access-point page (Wi-Fi setup) now has a "Перезавантажити / Reboot" line.

## 1.1.2 — 2026-11-14

- VPN WireGuard: можна вставити весь текст файлу клієнта — поля заповнюються самі; рядки DNS,
  AllowedIPs, PersistentKeepalive міст виставляє сам.
- Поля приватного й спільного ключа показують крапки.

- VPN WireGuard: paste the whole client file — the fields fill in by themselves; DNS,
  AllowedIPs and PersistentKeepalive are set by the bridge itself.
- Private and preshared key fields are masked.

## 1.1.1 — 2026-11-14

- Сервісна сторінка `/service` з кнопками «Перезавантажити міст» і «Скинути все» — працює і в
  домашній мережі, і в режимі точки доступу (`192.168.4.1/service`).

- Service page `/service` with "Restart the bridge" and "Reset all" buttons — works on the home
  network and in access-point mode (`192.168.4.1/service`).

## 1.1.0 — 2026-11-14

- **VPN WireGuard** на вкладці «VPN WireGuard»: свій сервер, ключі, адреса в тунелі; стан
  тунелю (вимкнено / з'єднується / з'єднано). Приватний ключ назад не показується ніде.
- Без налаштувань VPN вимкнений; недосяжний сервер міст не перезавантажує.
- Зміна Wi-Fi мережі чи «Скинути все» стирає й налаштування VPN.

- **WireGuard VPN** on the "VPN WireGuard" tab: your own server, keys, tunnel address; tunnel
  state (off / connecting / connected). The private key is never shown back.
- Without settings the VPN is off; an unreachable server never reboots the bridge.
- Joining another Wi-Fi network or "Reset all" also erases the VPN settings.

## 1.0.2 — 2026-11-14 — перша публічна версія / first public release

- Одна прошивка для всіх мостів, без чужих паролів і ключів усередині.
- Підключення до Wi-Fi через точку доступу `tclac-xxxxxx`; сторінка моста `http://tclac-xxxxxx.local`.
- Ключ для Home Assistant міст генерує сам; при підключенні до мережі з іншою назвою ключ
  змінюється (попередній власник доступу не зберігає). Кнопка «Скинути все».
- Пульт у стилі панелі Home Assistant (українська / English): круговий регулятор температури,
  режими, швидкість вентилятора (авто, тихий, 1–5), турбо, жалюзі вгору-вниз і вліво-вправо
  (гойдання й фіксовані положення — 72 комбінації), підсвітка дисплея, звук кнопок,
  самоочищення випарника (лише на вимкненому кондиціонері).
- Оновлення з цього репозиторію: міст перевіряє раз на добу, встановлення — кнопкою.

- One firmware for every bridge, with no third-party passwords or keys inside.
- Wi-Fi setup via the `tclac-xxxxxx` access point; bridge page at `http://tclac-xxxxxx.local`.
- The bridge generates its own Home Assistant key; joining a network with a different name
  changes the key (the previous owner loses access). "Reset all" button.
- Remote page in the style of a Home Assistant dashboard (Ukrainian / English): circular
  temperature dial, modes, fan speed (auto, quiet, 1–5), turbo, up-down and left-right louvers
  (swing and fixed positions — 72 combinations), display light, button beep, evaporator
  self-clean (only while the AC is off).
- Updates from this repository: checked once a day, installed with a button.
