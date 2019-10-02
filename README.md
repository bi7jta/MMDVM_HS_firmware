Detail view my BLOG 
[http://mmdvm.bi7jta.org/search/label/Firmware_upgrade](http://mmdvm.bi7jta.org/search/label/Firmware_upgrade)  
  
Upgrade/flash MMDVM repeater V3F446  
  
Open your ssh GUI http://pi-star/admin/expert/ssh_access.php  
User: pi-star  
Pass: raspberry  

Login and Ctrl + C then Contl +V ,run the follow script  

``` 
rpi-rw;  
curl -OL https://raw.githubusercontent.com/bi7jta/MMDVM_HS_firmware_VR2VYE/master/RepeaterV3F4/stm32flashV5;  
sudo chmod +x stm32flashV5;   
curl -OL https://raw.githubusercontent.com/bi7jta/MMDVM_HS_firmware_VR2VYE/master/RepeaterV3F4/mmdvm_f4.hex;  
sudo killall MMDVMHost >/dev/null 2>&1 ;  
sudo ./stm32flashV5 -v -w mmdvm_f4.hex  -R  -i 20,-21,21:-20,21 /dev/ttyAMA0;  
#Please Power off then Power on(Not the reboot).  
``` 

