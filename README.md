# Voice Alert System

A lightweight real-time keyword spotting application that listens via your microphone and sends instant notifications via Telegram. Powered by the offline Vosk speech recognition engine—100% on-device, with zero audio retention and zero cloud upload.

一款轻量级的离线语音关键词监控与即时提醒工具。通过麦克风监听声音输入，基于 Vosk 离线语音识别模型在本地实时捕捉自定义关键词并发送 Telegram 通知；音频仅在内存中流式分析，全程不录音、不落盘、不上传云端。

## 🚀 Features

- **Real-time Keyword Detection**: Continuously monitors microphone input to spot user-defined keywords with live streaming partial-result detection.
- **100% Offline Speech Recognition**: Uses the lightweight [Vosk](https://alphacephei.com/vosk/) engine (`vosk-model-small-cn-0.22`), running entirely on-device without external speech APIs.
- **Instant Alert Notifications**: Dispatches instant alerts to your designated Telegram chat when keywords are detected, featuring connection pooling and token masking.
- **User-Friendly GUI**: Built with [Flet](https://flet.dev/), providing a clean desktop interface, model downloader with live progress, and Chinese/English bilingual support.
- **Log Monitoring**: Real-time console log view with token sanitization to prevent credential leaks.

## 🔒 Privacy & Data Security

- **100% On-Device Processing**: Speech recognition runs entirely on your local machine using offline models.
- **Zero Audio Retention**: Microphone input is processed in volatile memory (RAM) for real-time inference. Audio frames are never saved to disk, recorded, or cached.
- **Zero Audio Upload**: Only the text notification message is transmitted to Telegram when a keyword triggers. No raw audio data is ever transmitted over the network.
- **Credential Protection**: Configuration and bot tokens remain local, and are automatically masked in log outputs.

## 🛠️ Technology Stack

- **[Python](https://www.python.org/)**: Core application runtime (3.10+).
- **[Flet](https://flet.dev/)**: Framework for building the cross-platform GUI.
- **[Vosk](https://alphacephei.com/vosk/)**: Offline speech recognition toolkit.
- **[PyAudio](https://people.csail.mit.edu/hubert/pyaudio/)**: Real-time microphone audio stream capture.
- **[Requests](https://requests.readthedocs.io/)**: HTTP library for notification delivery.
- **[PyInstaller](https://pyinstaller.org/)**: Standalone executable packaging.

## 📋 Prerequisites

- Python 3.10 or higher.
- A Telegram Bot Token and Chat ID (for receiving alerts).
- A working microphone.

## 📦 Installation

1. **Clone the repository** (if applicable) or download the source code:
   ```bash
   git clone https://github.com/AndrewWangDev/voice_check.git
   cd voice_check
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
   *Note: On Windows, you might need to install Visual C++ Build Tools for PyAudio if the wheel installation fails.*

## ▶️ Usage

1. **Run the application**:
   ```bash
   python gui.py
   ```

2. **Configure settings**:
   - **Telegram Bot Token**: Enter the bot token obtained from @BotFather.
   - **Chat ID**: Enter your personal or group Chat ID.
   - **Keywords**: Enter the keywords to monitor, separated by commas.
   - **Proxy (Optional)**: If needed for your network environment, configure an HTTP or SOCKS5 proxy (e.g., `http://127.0.0.1:7890` or `socks5://127.0.0.1:1080`). Leave blank if not required.

3. **Start Monitoring**:
   - Click the **Start Detection** (开始监听) button.
   - The application checks or downloads the offline Vosk model and begins real-time listening.
   - When a keyword is spotted, an alert is sent to Telegram and logged in the console.

4. **Stop Monitoring**:
   - Click **Stop Detection**  to gracefully close the audio stream.

## 🔨 Building (Optional)

To create a standalone executable:

```bash
python build.py
```
The executable will be generated in the `release/VoiceAlert` directory.

## ⚠️ Disclaimer

This project is developed and provided strictly for personal development, research, and educational purposes. Users are solely responsible for ensuring compliance with all applicable local laws and regulations regarding audio monitoring and privacy in their jurisdiction.

## 📄 License

This project is open-sourced under the [MIT License](LICENSE).
