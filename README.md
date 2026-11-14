# TCL Bridge — firmware

Готові прошивки моста TCL Bridge для оновлення «по повітрю».
Firmware builds for the TCL Bridge, used for over-the-air updates.

## Як оновлюється міст / How the bridge updates

- Міст раз на добу читає `manifest.json` із цього репозиторію.
- Якщо там новіша версія, на сторінці моста (вкладка «Мережа») і в Home Assistant
  з'являється кнопка «Оновити».
- Невдале оновлення нічого не ламає: міст лишається на попередній версії.

The bridge checks `manifest.json` once a day. When a newer version is listed, an "Update"
button appears on the bridge page (Network tab) and in Home Assistant. A failed update
leaves the previous version running.

## Файли / Files

- `manifest.json` — поточна версія / current version
- `firmware/` — файли прошивок / firmware images (ESP32-S3)

Тут немає вихідного коду й жодних особистих даних: прошивка однакова для всіх мостів.
No source code or personal data here: the image is identical for every bridge.
