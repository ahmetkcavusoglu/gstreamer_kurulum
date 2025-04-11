# GStreamer Nedir?

GStreamer, çoklu ortam uygulamaları oluşturmak için kullanılan güçlü bir açık kaynak multimedya çerçevesidir.

# Ne İçin Kullanılır?

GStreamer, ses ve video oynatma, kodlama, kod çözme, düzenleme ve yayın akışı gibi çeşitli multimedya işlemleri için kullanılır.

# GStreamer Kurulumu

GStreamer'ı şu adresten indirebilirsiniz: https://gstreamer.freedesktop.org/download/#windows 

MSVC 64-bit (VS 2019, Release CRT) sürümünü tercih edin:
- 1.26.0 runtime installer
- 1.26.0 development installer

![Installer](https://raw.githubusercontent.com/ahmetkcavusoglu/gstreamer_kurulum/refs/heads/master/images/001_installer_download.png)

Her iki installer'ı da indirip kurun. En güncel sürümü de indirebilirsiniz.

# Ortam Değişkenlerinin Ayarlanması

Kurulum tamamlandıktan sonra bilgisayarınızdan ortam değişkenlerine gidin:

1. Kullanıcı değişkenleri ve sistem değişkenleri kısmında ayrı ayrı Path'e tıklayın
2. GStreamer'ın kurulu olduğu dizinin içerisinde yer alan MSVC'nin aşağıdaki klasörlerini ekleyin:
   - bin
   - lib
   - lib\pkconfig
   - lib\gstreamer-1.0

Kullanıcı değişkenleri aşağıdaki gibi olmalıdır;

![Installer](https://github.com/user-attachments/assets/ab4573d1-6267-4216-a6ab-1b7e2dd72b70)

Ortam değişkenleri aşağıdaki gibi olmalıdır;

![Installer](https://github.com/user-attachments/assets/f96bc358-4e67-488e-ba52-94a3186e890b)

# Kurulumun Doğrulanması

Daha sonra bilgisayardan terminal açın. Terminalde aşağıdaki komutu çalıştırın:

gst-launch-1.0.exe --version

![Installer](https://github.com/ahmetkcavusoglu/gstreamer_kurulum/blob/master/images/004_komut_satiri_gstreamer_version.png?raw=true)
Uygun bir cevap gelirse kurulum başarılı demektir.

# Örnek Kullanım

Örnek olarak aşağıdaki komutu çalıştırabilirsiniz:

gst-launch-1.0 rtspsrc location="rtsp://admin:1234@192.168.1.200:554/cam/realmonitor?channel=1&subtype=0" ! rtph264depay ! avdec_h264 ! autovideosink

Yukarıdaki komut çalışmazsa, sonuna `.exe` ekleyerek deneyebilirsiniz:

gst-launch-1.0.exe rtspsrc location="rtsp://admin:1234@192.168.1.200:554/cam/realmonitor?channel=1&subtype=0" ! rtph264depay ! avdec_h264 ! autovideosink

![Installer](https://github.com/ahmetkcavusoglu/gstreamer_kurulum/blob/master/images/005_gstreamer_sample_using.png?raw=true)
