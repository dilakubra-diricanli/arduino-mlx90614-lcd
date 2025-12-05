# Arduino MLX90614 Infrared Thermometer / Arduino MLX90614 Kızılötesi Termometre

[![Arduino](https://img.shields.io/badge/Arduino-Compatible-blue.svg)](https://www.arduino.cc/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A professional Arduino-based infrared thermometer project using the MLX90614 sensor with I2C LCD display. This project demonstrates non-contact temperature measurement capabilities.

MLX90614 sensörü kullanılarak I2C LCD ekran ile geliştirilmiş profesyonel bir Arduino tabanlı kızılötesi termometre projesi. Bu proje temasız sıcaklık ölçümü yeteneklerini gösterir.

---

## 📋 Table of Contents / İçindekiler

- [Overview / Genel Bakış](#overview--genel-bakış)
- [Features / Özellikler](#features--özellikler)
- [Hardware Requirements / Donanım Gereksinimleri](#hardware-requirements--donanım-gereksinimleri)
- [Software Requirements / Yazılım Gereksinimleri](#software-requirements--yazılım-gereksinimleri)
- [Installation / Kurulum](#installation--kurulum)
- [Wiring Diagram / Bağlantı Şeması](#wiring-diagram--bağlantı-şeması)
- [Usage / Kullanım](#usage--kullanım)
- [Project Structure / Proje Yapısı](#project-structure--proje-yapısı)
- [Technical Specifications / Teknik Özellikler](#technical-specifications--teknik-özellikler)
- [Troubleshooting / Sorun Giderme](#troubleshooting--sorun-giderme)
- [Contributors / Katkıda Bulunanlar](#contributors--katkıda-bulunanlar)
- [License / Lisans](#license--lisans)

---

## Overview / Genel Bakış

This project implements a contactless infrared thermometer using the MLX90614 sensor module. The system measures object temperature without physical contact and displays the readings on both an I2C LCD screen and the Serial Monitor. The project was developed as part of a module project at Sivas Bilim ve Teknoloji Üniversitesi (SBTU).

Bu proje, MLX90614 sensör modülü kullanılarak temasız bir kızılötesi termometre uygular. Sistem, fiziksel temas olmadan nesne sıcaklığını ölçer ve okumaları hem I2C LCD ekranda hem de Serial Monitor'da gösterir. Proje, Sivas Bilim ve Teknoloji Üniversitesi (SBTU) modül projesi kapsamında geliştirilmiştir.

### Key Capabilities / Temel Yetenekler

- ✅ Non-contact temperature measurement / Temasız sıcaklık ölçümü
- ✅ Real-time display on LCD / LCD'de gerçek zamanlı gösterim
- ✅ Serial Monitor output / Serial Monitor çıktısı
- ✅ Celsius temperature readings / Santigrat sıcaklık okumaları
- ✅ Easy-to-use interface / Kullanımı kolay arayüz

---

## Features / Özellikler

### English
- **Non-Contact Measurement**: Measure temperature without touching the object
- **Dual Display**: Shows temperature on both LCD screen and Serial Monitor
- **Real-Time Updates**: Continuous temperature monitoring with 1-second intervals
- **I2C Communication**: Uses I2C protocol for efficient sensor and display communication
- **User-Friendly Interface**: Clear LCD display with temperature in Celsius
- **Customizable**: Easy to modify for different applications

### Türkçe
- **Temasız Ölçüm**: Nesneye dokunmadan sıcaklık ölçümü
- **Çift Ekran**: Hem LCD ekranda hem Serial Monitor'da sıcaklık gösterimi
- **Gerçek Zamanlı Güncelleme**: 1 saniye aralıklarla sürekli sıcaklık izleme
- **I2C İletişim**: Sensör ve ekran iletişimi için I2C protokolü kullanımı
- **Kullanıcı Dostu Arayüz**: Santigrat cinsinden net LCD gösterimi
- **Özelleştirilebilir**: Farklı uygulamalar için kolayca değiştirilebilir

---

## Hardware Requirements / Donanım Gereksinimleri

### Components / Bileşenler

| Component / Bileşen | Quantity / Miktar | Description / Açıklama |
|---------------------|-------------------|------------------------|
| Arduino Uno (or compatible) | 1 | Microcontroller board |
| MLX90614 Infrared Sensor | 1 | Non-contact temperature sensor |
| I2C LCD 16x2 Display | 1 | 16x2 character LCD with I2C backpack |
| Jumper Wires | ~10 | For connections |
| Breadboard (optional) | 1 | For prototyping |
| 5V Power Supply | 1 | For Arduino (USB or external) |

### Pin Connections / Pin Bağlantıları

| Arduino Pin | Connected To / Bağlantı |
|-------------|-------------------------|
| 5V | MLX90614 VIN, LCD VCC |
| GND | MLX90614 GND, LCD GND |
| A4 (SDA) | MLX90614 SDA, LCD SDA |
| A5 (SCL) | MLX90614 SCL, LCD SCL |

**Note / Not**: Both MLX90614 and LCD use I2C communication, so they share the same SDA and SCL lines.

**Not**: MLX90614 ve LCD'nin ikisi de I2C iletişimi kullandığı için aynı SDA ve SCL hatlarını paylaşırlar.

---

## Software Requirements / Yazılım Gereksinimleri

### Required Libraries / Gerekli Kütüphaneler

1. **Wire Library** (Built-in / Yerleşik)
   - I2C communication support

2. **LiquidCrystal_I2C Library**
   - Install via Arduino Library Manager
   - Search for: `LiquidCrystal_I2C` by Frank de Brabander

3. **Adafruit MLX90614 Library**
   - Install via Arduino Library Manager
   - Search for: `Adafruit MLX90614 Library`
   - Also install `Adafruit Unified Sensor` dependency

### Installation Steps / Kurulum Adımları

1. Open Arduino IDE
2. Go to **Sketch → Include Library → Manage Libraries**
3. Search and install:
   - `LiquidCrystal_I2C`
   - `Adafruit MLX90614 Library`
   - `Adafruit Unified Sensor` (dependency)

---

## Installation / Kurulum

### Step 1: Hardware Setup / Donanım Kurulumu

1. Connect MLX90614 sensor to Arduino:
   - VIN → 5V
   - GND → GND
   - SDA → A4
   - SCL → A5

2. Connect I2C LCD to Arduino:
   - VCC → 5V
   - GND → GND
   - SDA → A4
   - SCL → A5

3. Power up Arduino via USB or external power supply

### Step 2: Software Setup / Yazılım Kurulumu

1. Clone or download this repository
2. Install required libraries (see Software Requirements)
3. Open `mlx90614_infrared_project.ino` in Arduino IDE
4. Select your board: **Tools → Board → Arduino Uno**
5. Select your port: **Tools → Port → [Your Arduino Port]**
6. Upload the code to Arduino

---

## Wiring Diagram / Bağlantı Şeması

```
                    Arduino Uno
                       │
        ┌──────────────┼──────────────┐
        │              │              │
     MLX90614      I2C LCD        USB
        │              │              │
     VIN→5V        VCC→5V             │
     GND→GND       GND→GND            │
     SDA→A4        SDA→A4             │
     SCL→A5        SCL→A5             │
```

**Important / Önemli**: 
- Ensure I2C addresses don't conflict (default LCD: 0x27, MLX90614: 0x5A)
- I2C adreslerinin çakışmadığından emin olun (varsayılan LCD: 0x27, MLX90614: 0x5A)

---

## Usage / Kullanım

### Basic Operation / Temel Kullanım

1. **Power On / Açılış**: 
   - Connect Arduino to power
   - LCD will display "HELLO SBTU" and "GROUP 4" for 3 seconds
   - Arduino'yu güce bağlayın
   - LCD 3 saniye boyunca "HELLO SBTU" ve "GROUP 4" gösterecek

2. **Temperature Measurement / Sıcaklık Ölçümü**:
   - Point the MLX90614 sensor towards the object
   - Wait for stable reading (sensor needs ~1 second)
   - Temperature displays on LCD and Serial Monitor
   - MLX90614 sensörünü nesneye doğrultun
   - Kararlı okuma için bekleyin (sensör ~1 saniye gerektirir)
   - Sıcaklık LCD ve Serial Monitor'da görüntülenir

3. **Serial Monitor / Serial Monitor**:
   - Open Serial Monitor in Arduino IDE (9600 baud)
   - View temperature readings in real-time
   - Arduino IDE'de Serial Monitor'u açın (9600 baud)
   - Sıcaklık okumalarını gerçek zamanlı görüntüleyin

### LCD Display Format / LCD Ekran Formatı

```
Line 1: MODULE PROJECT
Line 2: Temp: XX.XX°C
```

---

## Project Structure / Proje Yapısı

```
arduino-mlx90614-infrared-thermometer/
│
├── mlx90614_infrared_project.ino  # Main Arduino sketch
├── README.md                       # Project documentation
├── MODULE PROJECT REPORT.docx      # Project report (Turkish)
├── MODULE PROJECT.pptx             # Project presentation
└── modül.vlog.mp4                  # Project video log
```

### Code Structure / Kod Yapısı

- **setup()**: Initializes serial communication, MLX90614 sensor, and LCD display
- **loop()**: Continuously reads temperature and updates displays every second
- **setup()**: Serial iletişimi, MLX90614 sensörü ve LCD ekranı başlatır
- **loop()**: Her saniye sıcaklığı okur ve ekranları günceller

---

## Technical Specifications / Teknik Özellikler

### MLX90614 Sensor / MLX90614 Sensörü

- **Temperature Range**: -70°C to +380°C (object)
- **Accuracy**: ±0.5°C (at room temperature)
- **Field of View**: 90° cone
- **Response Time**: < 1 second
- **Interface**: I2C (default address: 0x5A)
- **Supply Voltage**: 3V - 5V

### LCD Display / LCD Ekran

- **Type**: 16x2 Character LCD
- **Interface**: I2C (default address: 0x27)
- **Backlight**: LED backlight
- **Supply Voltage**: 5V

### Arduino Configuration / Arduino Yapılandırması

- **Board**: Arduino Uno (or compatible)
- **Clock Speed**: 16 MHz
- **Operating Voltage**: 5V
- **Serial Baud Rate**: 9600

---

## Troubleshooting / Sorun Giderme

### Common Issues / Yaygın Sorunlar

#### 1. LCD Not Displaying / LCD Görüntülemiyor

**Problem / Sorun**: LCD screen is blank or shows garbage characters

**Solutions / Çözümler**:
- Check I2C address (default: 0x27). Use I2C scanner sketch to verify
- Verify wiring connections (VCC, GND, SDA, SCL)
- Adjust LCD contrast potentiometer (if available)
- I2C adresini kontrol edin (varsayılan: 0x27). Doğrulamak için I2C scanner sketch'i kullanın
- Bağlantıları kontrol edin (VCC, GND, SDA, SCL)
- LCD kontrast potansiyometresini ayarlayın (varsa)

#### 2. Sensor Not Reading / Sensör Okumuyor

**Problem / Sorun**: Temperature readings are 0 or incorrect

**Solutions / Çözümler**:
- Verify MLX90614 wiring (especially SDA and SCL)
- Check I2C address (default: 0x5A)
- Ensure sensor is pointing at an object (not empty space)
- Wait for sensor stabilization (~1-2 seconds)
- MLX90614 bağlantılarını kontrol edin (özellikle SDA ve SCL)
- I2C adresini kontrol edin (varsayılan: 0x5A)
- Sensörün bir nesneye doğrultulduğundan emin olun (boş alana değil)
- Sensör stabilizasyonu için bekleyin (~1-2 saniye)

#### 3. Serial Monitor Issues / Serial Monitor Sorunları

**Problem / Sorun**: No output in Serial Monitor

**Solutions / Çözümler**:
- Verify baud rate is set to 9600
- Check USB cable connection
- Ensure correct COM port is selected
- Baud rate'in 9600 olarak ayarlandığını kontrol edin
- USB kablo bağlantısını kontrol edin
- Doğru COM port'un seçildiğinden emin olun

#### 4. I2C Address Conflict / I2C Adres Çakışması

**Problem / Sorun**: Only one device works

**Solutions / Çözümler**:
- Use I2C scanner to detect all devices
- Verify addresses: LCD (0x27), MLX90614 (0x5A)
- Check if multiple devices share same address
- Tüm cihazları tespit etmek için I2C scanner kullanın
- Adresleri doğrulayın: LCD (0x27), MLX90614 (0x5A)
- Birden fazla cihazın aynı adresi paylaşıp paylaşmadığını kontrol edin

---

## Contributors / Katkıda Bulunanlar

- **Group 4** - Sivas Bilim ve Teknoloji Üniversitesi (SBTU)
- Module Project Team

---

## License / Lisans

This project is open source and available under the MIT License.

Bu proje açık kaynaklıdır ve MIT Lisansı altında kullanılabilir.

---

## Acknowledgments / Teşekkürler

- Adafruit for the MLX90614 library
- Sivas Bilim ve Teknoloji Üniversitesi (SBTU) for project support
- MLX90614 kütüphanesi için Adafruit'e
- Proje desteği için Sivas Bilim ve Teknoloji Üniversitesi (SBTU)'ye

---

## Contact / İletişim

For questions or support, please refer to the project documentation or contact the development team.

Sorularınız veya destek için lütfen proje dokümantasyonuna bakın veya geliştirme ekibiyle iletişime geçin.

---

**Last Updated / Son Güncelleme**: 2024

**Version / Sürüm**: 1.0

