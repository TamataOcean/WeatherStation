## TamataWeather Station with CoolCo Board, using grafana, influxdb & mosquitto 

![CoolCo_Weather_Station](https://user-images.githubusercontent.com/25310798/71003236-0b726c00-20e1-11ea-80fb-34e6f4bc5d11.jpg)

### Data Collecting from sensors.
- Temperature In/Out  
- Atmospheric Pressure  
- Light intensity, UV, IR, 
- Transfert data by JSON export.  

### System task Scheduling.
- Control & Reporting
- Log activities
- Control & Alert System to send alert (color, temperature, light from standard deviation) 

### Install save_data.js as a service
#### Into : /lib/systemd/system 
     [Unit]
      Description=TamataWeatherStation
      After=multi-user.target

      [Service]
      WorkingDirectory=/home/pi/code/WeatherStation/systools
      ExecStart=/usr/bin/node save_data.js
      Restart=on-failure

      [Install]
      WantedBy=multi-user.target

#### Declare service  
      sudo systemctl enable tamata_weatherstation.service  

#### Start service  
      sudo systemctl start tamata_weatherstation.service  

#### Log Service
      sudo journalctl -u tamata_weatherstation.service 

## Buy us a beer!

This FLOSS software is funded by donations only. Please support us to maintain and further improve it!

<a href="https://liberapay.com/TamataOcean/donate"><img alt="Donate using Liberapay" src="https://liberapay.com/assets/widgets/donate.svg"></a>


Much more information about the self-sufficienty challenge : [TamataOcean](http://tamataocean.com)  
[contact@tamataocean.com](mailto:contact@tamataocean.com)
  
