# ECGXMLReader

Python class for reading ECG XML files. Extracts lead voltages, and optionally augments 12L from 8L (common in GE MUSE XML).

## Dependencies
Requires the following libraries:

- xmltodict
- numpy

## Usage
ECGXMLReader can be called by other Python scripts and used to get raw voltage values from compressed formats.
```
from ECGXMLReader import ECGXMLReader

ecg = ECGXMLReader('ecg_file.xml', augmentLeads=True)

print( ecg.getLeadVoltages('I') )
```

## Structure
* ECGXMLReader
  * PatientDemographics
    * PatientID
    * DateOfBirth
    * Gender
    * HeightCM
    * WeightKG
    * PatientLastName
  * TestDemographics
    * DataType
    * Site
    * AcquisitionDevice
    * Status
    * AcquisitionTime
    * AcquisitionDate
    * CartNumber
    * AcquisitionSoftwareVersion
  * RestingECGMeasurements
    * ECGSampleBase
    * ECGSampleExponent
  * Waveform
    * WaveformType
    * WaveformStartTime
    * NumberOfLeads
    * SampleType
    * SampleBase
    * SampleExponent
    * LeadData
      * LeadByteCountTotal
      * LeadTimeOffset
      * LeadSampleCountTotal
      * LeadAmplitudeUnitsPerBit
      * LeadAmplitudeUnits
      * LeadHighLimit
      * LeadLowLimit
      * LeadID
      * LeadOffsetFirstSample
      * FirstSampleBaseline
      * LeadSampleSize
      * LeadOff
      * BaselineSway
      * LeadDataCRC32
      * WaveFormData
