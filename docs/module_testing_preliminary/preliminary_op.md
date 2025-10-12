 **Preliminary Operations **

Software:

* [Dirigent](https://gitlab.cern.ch/cms_tk_ph2/dirigent)
    * A software wrapper, wrapping together Ph2_ACF (DAQ software) and icicle (software for PS controlling)
* [Ph2_ACF](https://gitlab.cern.ch/cms_tk_ph2/ph2_acf)
    * DAQ software has to be installed independently, look for the latest tagged version for IT 
* [POWDER](https://gitlab.cern.ch/cms_tk_ph2/power_supply)
    * Power supply libraries that is needed only to work with the CAEN LV
* [DataBase_pythonUploader](https://gitlab.cern.ch/cms-ph2-database/py4dbupload)
    * This is needed to upload and edit the modules that are assembled in Firenze to the central [DCA](https://cmsdca.cern.ch/trk_cmsr/construct/parts/). Now in order to have the macro working you must be registered to the various e-groups related to the database([Assembly Operator](https://e-groups.cern.ch/e-groups/Egroup.do?egroupId=10371208&AI_USERNAME=GBARDELL&searchField=0&searchMethod=1&searchValue=cms-tracker&pageSize=100&hideSearchFields=false&searchMemberOnly=false&searchAdminOnly=false&AI_SESSION=A14D2513EC1D9B7E5E74DC59856C84FE), [QC Operator](https://e-groups.cern.ch/e-groups/Egroup.do?egroupId=10371211&AI_USERNAME=DIMATTIA&searchField=0&searchMethod=0&searchValue=cms-&pageSize=30&hideSearchFields=false&searchMemberOnly=false&searchAdminOnly=true&AI_SESSION=BFhKdxLwOasNLkbBtvtWK6ZpHHvuZeQV93Y-JFCAYJz2clVK7nQH%2114215125%21wlsmanaged1%2110110%2110111%211603272119128) and [Tracking Operator](https://e-groups.cern.ch/e-groups/Egroup.do?egroupId=10371211&AI_USERNAME=DIMATTIA&searchField=0&searchMethod=0&searchValue=cms-&pageSize=30&hideSearchFields=false&searchMemberOnly=false&searchAdminOnly=true&AI_SESSION=BFhKdxLwOasNLkbBtvtWK6ZpHHvuZeQV93Y-JFCAYJz2clVK7nQH%2114215125%21wlsmanaged1%2110110%2110111%211603272119128)). Also while downloading the macro the user must be enrolled in such e-groups.
* [Panthera](https://panthera.fit.edu/)
    * A panthera account is needed to upload the module to the site and eventually review them. To ask for an account you have to write a mail to Scott Demarest and Souvik Das, where you can also ask different roles.

Hardware:
* Base plate for testing
* Testing Adapter screwed to the base plate 
* Needle card mounted on the adc and adapter
* 3 long spines and 1 short and a USB-A cable
* Clamp 3D printed

First visual inspect the module, the wire-bondings, the status of connectors of the assembled modules. Place the module in the base plate, close the power connector in the Testing adapter, close with the clamp and screw it to the base plate using flat screw otherwise the needle card will not be able to reach the module. Place the four spines, taking care of placing the small one as it's illustrated in the picture. Attach the usb cable, and enable its usb port, if it's not done, with: 
``` 
sudo chmod 777 /dev/ttyUSB* 
```

After downloading and having installed dirigent and Ph2_ACF source first on dirigent and later on Ph2_ACF. It can be that the root version downloaded in the pc is from a binary distribution, dirigent in that case has to be compiled with the -c flag. Check that the icicle version works, by trying to talk with an instrument, as example:
```
tti -R "resource_name" status"
``` 

Copy the config files on available in the config file of dirigent. The modules.json file has to be adapted for the module studied (double or quad). Example for double:
```
{
        "Hybrid": {
                "0": {
                        "RD53Bv2": {
                                "info" : {"module_name" : "C2HQ0", "type" : "1x2", "subdetector" : "TBPX", "sensor" : true},
                                "0": {"Lane": 0, "eFuseCode": 46721, "LaneConfig": {"outputLanes": "0100"}, "Settings": {"VOLTAGE_TRIM_DIG": 7, "VOLTAGE_TRIM_ANA": 9, "VREF_ADC": 844}},
                                "1": {"Lane": 3, "eFuseCode": 46721, "LaneConfig": {"outputLanes": "0100"}, "Settings": {"VOLTAGE_TRIM_DIG": 7, "VOLTAGE_TRIM_ANA": 9, "VREF_ADC": 844}}
                        }
                }
        }
}
```

The instruments.json file has to be adapted for the instruments used, the lv, the keithley, the cold box and the needle card, according to the examples below:
```
instruments": {
                "lv_1": {
                        "class": "TTITSX",
                        "resource": "TCPIP::192.168.0.22::9221::SOCKET",
                        "sim": false,
                        "default_voltage": 4.0,
                        "default_current": 3.7,
                        "wait_time": 5
                },
                "hv_1": {
                        "class": "Keithley2410",
                        "resource": "ASRL/dev/ttyUSB0::INSTR",
                        "sim": false,
                        "default_voltage": -50,
                        "default_current": 10e-6,
                        "default_range": -80
                },
                "ab_1": {
                        "class": "ETHProbecard",
                        "resource": "ASRL/dev/ttyUSB2::INSTR"
                }
        },
```

The dirigent.toml file has to be adapted according to the tests that are going to be performed. The first test used is get_module_info to retrieve the information of the modules. It's launched via the command below, where the flag -r is meant to overwrite  the parameters of the json and -e to overwrite the e-fuse code of the modules.json. This will try to read the module and by the efuse codes it will download the information from the database.   
```
dirigent -C dirigent.toml get_module_info -r 1 -e 1
```


The most common scans are the iv_curve scan, with limit imposed to -80 V for 3D and to -350 V for planar. In the scan the flag monitor_temperature has to be set true such that the temperature is registered at the end of the scan. At the moment it's possible to increase the time of the measurements, through the flag temp_runtime to 20, and launching the scan with 
```
dirigent -C dirigent.toml iv_curve -t 20
```
This is done to guarantee enough time to Ph2_ACF such that it's able to save correctly the monitoring files 

[← Back to main page](../index.md)
