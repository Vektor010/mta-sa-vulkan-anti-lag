<div align="center">
  <img src="https://raw.githubusercontent.com/Vektor010/mta-sa-vulkan-anti-lag/master/assets/banner.jpg" alt="MTA Vulkan Overdrive Banner" width="100%" style="border-radius: 15px; box-shadow: 0 0 20px rgba(0,255,128,0.5);">
  <br><br>
  <h1>🔥 MTA: VULKAN OVERDRIVE 🔥</h1>
  
  <p>
    <a href="https://github.com/Vektor010/mta-sa-vulkan-anti-lag/releases/latest"><img src="https://img.shields.io/badge/Release-v1.10.3_Async-FF007F?style=for-the-badge&logo=github&logoColor=white" alt="Version"></a>
    <img src="https://img.shields.io/badge/Platform-MTA:SA-8A2BE2?style=for-the-badge&logo=windows&logoColor=white" alt="Platform">
    <img src="https://img.shields.io/badge/API-Vulkan_(DXVK)-00FFFF?style=for-the-badge&logo=vulkan&logoColor=black" alt="API">
  </p>

  <h3>Ультимативный фикс лагов, фризов и просадок FPS для любого сервера MTA (2026)</h3>
</div>

---

## 🛑 В чем проблема: Почему MTA фризит даже на мощных ПК?
> [!WARNING]
> **Главная проблема - это игра 2004 года.** MTA:SA работает на древнем DirectX 9 (2004 года). Этот старый графический API физически не умеет использовать **вашу видеокарту**, из-за чего она "простаивает", а игра фризит (статтерит) и выдает низкий фреймрейт на 3-5%. А процессор - задыхается и долбится в потолок на одном ядре (нагрузка до 100%).

## ✅ Наше решение: ПЕРЕХОД НА VULKAN API (DXVK ASYNC)
> [!TIP]
> **Как работает этот патч?** Он полностью заменяет ядро по обработке графики DirectX 9 на современный графический стандарт **Vulkan** с технологией **Async**. 
> Версия **DXVK-Async** лучше стандартной, так как она отправляет компиляцию шейдеров (новых машин и текстур) в фоновые потоки процессора. Это полностью убивает фризы при прогрузке толпы игроков на сервере!

---

## 📈 Доказательства работы (Фото в студию)
Мои скриншоты реальной работы патча (библиотеки DXVK) на тяжелом сервере:

<div align="center">
  <img src="https://raw.githubusercontent.com/Vektor010/mta-sa-vulkan-anti-lag/master/assets/dxvk-proof-legendary.jpg" alt="DXVK HUD Proof" style="border: 2px solid #00ffff; border-radius: 12px; margin: 20px 0;">
</div>

Слева зелёный график, в свойствах, он показывает работу вашего железа:

| Показатель HUD | На стандартной игре (Без патча) | На игре под патчем при онлайне (Без обмана) |
| :--- | :--- | :--- |
| 🟢 **Зеленая линия** | Ужасный Jitter и рванный фреймтайм. Жесткие постоянные фризы (FrameTime). | **Всё ровно прям.** Линия прямая - картинка максимально без фризов. Движения плавные, как масло. |
| 🚀 **min: 8.8 max: 18.3** | Скачки FrameTime. Огромный max 18.3ms обеспечивают 1% Low не выше 54 FPS в людном месте. | **Скачки не ощутимы.** Даже когда вы въезжаете в толпу людей, FPS не проседает ниже комфортных значений. |
| 💻 **GPU: 3%** | Искусственно заниженный CPU-bottleneck. Убогая технология трансляции SPIR-V шейдеров. | **Нагрузки нет.** Ваша видеокарта дышит во всю мощьность. Ядра дышат, и выдается весь еe потанцевал. |
| 🧠 **Vidmem heap 0** | Проблемы VRAM, переполнение памяти. Классические утечки памяти (Memory Leaks) D3D9. | **Память в норме.** Игра стабильно работает из-за отличной работы памяти через патч. |
| 📈 **FPS: 73.9** | Устаревшие методы отрисовки занижают возможный максимальный кадров. | **Летающий фпс.** FPS вырос как минимум на половину, картинка стабильна (без разрывов). |

---

## 🛠 Как установить на компьютер (За 1 минуту)

Специально подготовленный патч - скачивай одним кликом. Мы уже настроили нужный конфиг в этом ZIP-файле.

<div align="center">
  <br>
  <a href="https://github.com/Vektor010/mta-sa-vulkan-anti-lag/releases/download/v1.10.3-mta/MTA_Vulkan_Patch.zip">
    <img src="https://img.shields.io/badge/СКАЧАТЬ_ГОТОВЫЙ_ПАТЧ_(ZIP)-FF007F?style=for-the-badge&logo=download&logoColor=white" alt="Download Button">
  </a>
  <br><br>
</div>

> [!WARNING]
> **Почему нужно качать именно 1.10.3 Async?**
> MTA:SA - это старая 32-битная игра. Версия 1.10.3 является **последней стабильной версией DXVK**, которая идеально поддерживает 32-битные архитектуры (x86) без багов. Версия Async добавляет фоновую компиляцию для устранения статтеров. Новые версии приведут к вылетам!

1. Скачайте по кнопке выше, белый логотип **MTA_Vulkan_Patch.zip**.
2. Извлеките архив. Внутри будет два файла: **d3d9.dll** и **dxvk.conf**.
3. Скопируйте эти файла в **корневую папку игрушки GTA San Andreas** (туда, где лежит **gta_sa.exe**).

*(Для справки: мы взяли забазированный [оригинальный релиз DXVK 1.10.3 от doitsujin](https://github.com/doitsujin/dxvk/releases/tag/v1.10.3) и добавили туда x32/d3d9.dll с поддержкой Async).*

> [!IMPORTANT]
> **Бросать патч нужно в папку с чистой GTA San Andreas**, а не в папку дополнительных файлов MTA!

Всё! Заходите на ваш сервер и наслаждайтесь 60+ FPS без лагов.

---

### 👁 Как мне убрать графики (отключить информацию)
> [!NOTE]  
> По дефолту HUD запускается с игрой визуально, чтобы вы оценили плавный график работы патча. Если он мешает обзору или бьет по вау-эффекту:
> 1. Откройте файл в папке.
> 2. Найдите файл **dxvk.conf**. 
> 3. Там заменяете строчку dxvk.hud = fps,frametimes,memory,gpuload,version,compiler на dxvk.hud = compiler. Вы восхитительны!

---

## 🚫 Что делать серверам с античитом
Если ваш сервер не пускает RP-сервер система защиты или не разрешает этот **d3d9.dll**:
* Напишите к разработчику проекта с просьбой добавить наш файл **d3d9.dll** (от библиотеки DXVK) в **Whitelist (белый список)** их сервера.
* Админы серверов вы можете по инструкции пула [#5342](https://github.com/multitheftauto/mtasa-blue/pull/5342) разработчиков игры MTA, которые выдают встроить это нововведение прямо внутри в саму игру.




---
<div align="center">
  <h2>Залетай на огонек для связи! 💬</h2>
  
  <p><b>Вступай в наш Telegram-чат для обмена опытами, ошибок и предложений по нашему проекту:</b></p>
  <a href="https://t.me/mtalivechat">
    <img src="https://img.shields.io/badge/Telegram-MTA_LIVE_CHAT-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram Channel">
  </a>
</div>
