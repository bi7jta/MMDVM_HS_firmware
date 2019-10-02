Detail view my BLOG [http://mmdvm.bi7jta.org/search/label/Firmware_upgrade](http://mmdvm.bi7jta.org/search/label/Firmware_upgrade)  
  
Upgrade/flash MMDVM repeater V3F446  
  
Open your ssh GUI http://pi-star/admin/expert/ssh_access.php  
User: pi-star  
Pass: raspberry  

Login and Ctrl + C then Contl +V ,run the follow script  

``` 
rpi-rw;  
curl -OL https://www.bi7jta.org/files/MMDVM_Firmware/repeater_HAT/MMDVM_REP_12.0MHz_v1.4.7_build_20191002.hex;  
sudo killall MMDVMHost >/dev/null 2>&1 ;  
sudo stm32flash -v -w MMDVM_REP_12.0MHz_v1.4.7_build_20191002.hex  -R  -i 20,-21,21:-20,21 /dev/ttyAMA0;  
``` 
