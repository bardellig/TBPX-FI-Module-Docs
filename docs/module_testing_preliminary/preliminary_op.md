# **IT 3D Flip-CHIP IV procedure**

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
* Adapter screwed to the base plate 
* Needle card mounted on the adc and adapter
* 3 long spines and 1 short and a USB-A cable

[← Back to main page](../index.md)
