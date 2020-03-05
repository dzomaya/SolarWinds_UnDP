# SolarWinds_UdNP
A repository for files related to SolarWinds. Using for examples on Thwack. 
The UdNP files here should be tested and modified as needed before production use.
Files are provided as-is, no warranty, and no guarantee of support.
Files posted  here were tested on Orion Platform 2019.2 HF2, NPM 12.5 and 15.x.x WEBCARDLX firmware.

These UnDPs were created for single phase Tripp Lite UPSes and PDUs using the "LX" network management card platform (e.g. the WEBCARDLX). There on some "GetNext" polls on SNMP table values that won't work quite right on devices with more than one input/output phase. I'd like to make better baseline UnDPs over time, so feel free to ping me with feedback here or on Thwack. 

## The files

### TrippLite_Single_Phase_PDU_Alpha.UnDP
This UnDP monitors:
* tlpAlarmsPresent - Should be 0 normally and > 0 if an alarm condition exists.
* tlpUpsBatteryStatus- The current status of the UPS batteries (Normal, Low, Depelted, or Unknown)
* tlpUpsOutputSource- The current source of the UPS output. "Normal" is the standard/ok value. Other possible values include      unknown, other, none, bypass, battery, boosting, reducing, second, and economy.                
* tlpUpsInputPhaseVoltage- The input voltage reported with granularity to the tenths place (e.g. 1251 = 125.1 volts)
* tlpUpsOutputPhaseVoltage- The output voltage reported with granularity to the tenths place (e.g. 1251 = 125.1 volts)
* tlpUpsOutputLinePercentLoad- The current output load as a percentage of total supported load.
* tlpUpsOutputLinePower- The current output wattage. 

This UnDP also has two "Converted" pollers that transform the input and output voltages to their decimal values. This should make creating graphs a little easier. 

### TrippLite_Single_Phase_PDU_Alpha.UnDP
This UnDP monitors:
* tlpAlarmsPresent - Should be 0 normally and > 0 if an alarm condition exists.
* tlpPduInputPhaseVoltage- The input voltage reported with granularity to the tenths place (e.g. 1251 = 125.1 volts)
* tlpPduOutputPhaseVoltage- The output voltage reported with granularity to the tenths place (e.g. 1251 = 125.1 volts)
* tlpPduOutputCurrent- The output amperage

This UnDP also has two "Converted" pollers that transform the input and output voltages to their decimal values. This should make creating graphs a little easier. 

## Looking for the Tripp Lite MIBs?
You can find them here:
https://www.tripplite.com/products/management-utilities
The MIBs contain the authoriative descriptions of the values used by these pollers. 

## Note: I work at Tripp Lite
