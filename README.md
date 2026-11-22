<div align="center">

# KRABER

**Лёгкий и быстрый реплей-буфер и редактор игровых откатов для Windows**  
**Lightweight, zero-bloat gameplay replay buffer & clip editor for Windows**

[![Latest Release](https://img.shields.io/github/v/release/tutposhka/kraber-record?style=for-the-badge&color=8b5cf6&label=Release)](https://github.com/tutposhka/kraber-record/releases/latest)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0ea5e9?style=for-the-badge&logo=windows)](#)
[![Built With](https://img.shields.io/badge/Rust%20%2B%20Tauri%202.0-f97316?style=for-the-badge&logo=rust)](#)

### [Скачать последнюю версию / Download Latest (Kraber-setup.exe)](https://github.com/tutposhka/kraber-record/releases/latest/download/Kraber-setup.exe)

[Русский](#-русский) • [English](#-english)

</div>

---

## 🇷🇺 Русский

**Kraber** — нативная десктопная утилита для мгновенного сохранения игровых откатов без нагрузки на систему и тяжёлых фоновых сервисов. Написана на **Rust + Tauri 2.0 + React**.

### Основные возможности
* **Аппаратный захват 60 FPS (DXGI Desktop Duplication):** жёсткая привязка к монитору с игрой и фиксированный выходной холст с GPU-масштабированием (`ID3D11VideoProcessorBlt`). Никаких зависаний при Alt-Tab и корректная запись растянутых разрешений (`4:3`, `5:4`, `1440x1080`, `1151x1080`) на весь экран без чёрных полос.
* **Умный режим ожидания (Smart Idle):** когда ни одна игра из белого списка не запущена, захват и кодировщик полностью спят и потребляют **0% GPU**.
* **Аппаратное кодирование:** автоматический выбор лучшего доступного энкодера (`NVENC` для NVIDIA, `AMF` для AMD, `QuickSync` для Intel, `x264` как резерв).
* **3 независимые аудиодорожки с синхронизацией по таймеру:**
  1. **Игра** — чистый звук игрового процесса.
  2. **Система / Discord / Браузер** — общение в войсе и фоновая музыка.
  3. **Микрофон** — фазо-непрерывный ресэмплинг в 48 kHz и плавный Noise Gate (`Attack / Hold / Release`), не обрезающий начало и концы слов.
* **Встроенный плеер, обрезка и монтаж:**
  * Раздельное управление громкостью и включением каждой из 3 дорожек при экспорте.
  * Быстрые закладки моментов в игре (`F8`) с отображением маркеров на таймлайне.
  * Кадрирование в вертикальный формат **`9:16 Split`** (увеличенный прицел сверху + полный экран снизу) для TikTok / Shorts / Reels.
  * Сжатие в один клик под лимит **Discord (< 10 МБ)** и копирование готового файла прямо в буфер обмена.
* **Автообновления:** встроенная проверка релизов с GitHub и установка обновлений в один клик прямо из приложения.

### Установка и первый запуск
1. Скачайте [**Kraber-setup.exe**](https://github.com/tutposhka/kraber-record/releases/latest/download/Kraber-setup.exe).
2. При первом запуске Windows SmartScreen может показать предупреждение *«Система Windows защитила ваш компьютер»* (из-за отсутствия платной подписи Microsoft) — нажмите **Подробнее → Выполнить в любом случае**.
3. После установки все будущие обновления будут прилетать автоматически внутри программы.

### Горячие клавиши по умолчанию
* `F9` — Сохранить откат (последние N секунд из буфера)
* `F8` — Поставить временную метку (закладку) на таймлайне

---

## 🇬🇧 English

**Kraber** is a native, lightweight gameplay replay buffer and clip editor for Windows, built with **Rust + Tauri 2.0 + React** for maximum FPS and zero background bloat.

### Key Features
* **Hardware 60 FPS Capture (DXGI Desktop Duplication):** Locks strictly onto the active game monitor with a fixed output canvas and GPU-accelerated scaling (`ID3D11VideoProcessorBlt`). Zero freezes on Alt-Tab and native full-screen recording for stretched resolutions (`4:3`, `5:4`, `1440x1080`, `1151x1080`) without black bars.
* **Smart Idle Mode:** When no whitelisted game is running, the capture pipeline and encoder sleep completely, consuming **0% GPU**.
* **Hardware Video Encoding:** Automatic encoder detection with priority fallback (`NVENC` for NVIDIA, `AMF` for AMD, `QuickSync` for Intel, `x264` CPU fallback).
* **3 Isolated Audio Tracks with Master Clock Sync:**
  1. **Game Audio** — isolated gameplay sound.
  2. **System / Discord / Browser** — voice comms and background audio.
  3. **Microphone** — phase-continuous 48 kHz resampling with a smooth `Attack / Hold / Release` Noise Gate that never clips word endings.
* **Built-in Clip Editor & Montage:**
  * Individual volume sliders and export toggles for all 3 audio tracks.
  * In-game moment bookmarking (`F8`) displayed as timeline markers.
  * **`9:16 Split`** vertical crop preset (zoomed crosshair on top + full gameplay screen on bottom) ready for Shorts / TikTok / Reels.
  * One-click **Discord compression (< 10 MB)** and direct clipboard file copy.
* **Seamless Auto-Updates:** Built-in GitHub Releases updater with one-click download and restart.

### Installation
1. Download [**Kraber-setup.exe**](https://github.com/tutposhka/kraber-record/releases/latest/download/Kraber-setup.exe).
2. On first launch, if Windows SmartScreen appears, click **More info → Run anyway**.
3. Once installed, future updates are delivered and installed automatically inside the app.

### Default Hotkeys
* `F9` — Save replay clip
* `F8` — Drop a timeline bookmark during gameplay
