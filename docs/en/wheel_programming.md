---
layout: default
title: FFB wheel communication
parent: FFB wheel DIY
nav_order: 5
---

- TOC
  {:toc}

---

There is a possibility for custom USB communication with device.
All types and constants needed for communication are described in header file:

### Custom HID types and constants

``` C
#define USB_VID                             1115
#define WHEEL_PID_FS                        22999

enum {
    INTERFACE_VENDOR = 0,
    INTERFACE_JOYSTICK = 1
};

typedef enum ExtensionModeEnum {
    EXTENSION_MODE_NONE = 0,
    EXTENSION_MODE_CUSTOM = 1,
} ExtensionModeEnum;

typedef enum SettingsFieldEnum {
    SETTINGS_FIELD_DIRECT_X_CONSTANT_DIRECTION = 0,
    SETTINGS_FIELD_DIRECT_X_SPRING_STRENGTH = 1,
    SETTINGS_FIELD_DIRECT_X_CONSTANT_STRENGTH = 2,
    SETTINGS_FIELD_DIRECT_X_PERIODIC_STRENGTH = 3,
    SETTINGS_FIELD_TOTAL_EFFECT_STRENGTH = 4,
    SETTINGS_FIELD_MOTION_RANGE = 5,
    SETTINGS_FIELD_SOFT_STOP_STRENGTH = 6,
    SETTINGS_FIELD_SOFT_STOP_RANGE = 7,
    SETTINGS_FIELD_STATIC_DAMPENING_STRENGTH = 8,
    SETTINGS_FIELD_SOFT_STOP_DAMPENING_STRENGTH = 9,
    SETTINGS_FIELD_FORCE_ENABLED = 11,
    SETTINGS_FIELD_DEBUG_TORQUE = 12,
    SETTINGS_FIELD_AMPLIFIER_GAIN = 13,
    SETTINGS_FIELD_CALIBRATION_MAGNITUDE = 15,
    SETTINGS_FIELD_CALIBRATION_SPEED = 16,
    SETTINGS_FIELD_POWER_LIMIT = 17,
    SETTINGS_FIELD_BRAKING_LIMIT = 18,
    SETTINGS_FIELD_POSITION_SMOOTHING = 19,
    SETTINGS_FIELD_SPEED_BUFFER_SIZE = 20,
    SETTINGS_FIELD_ENCODER_DIRECTION = 21,
    SETTINGS_FIELD_FORCE_DIRECTION = 22,
    SETTINGS_FIELD_POLE_PAIRS = 23,
    SETTINGS_FIELD_ENCODER_CPR = 24,
    SETTINGS_FIELD_P_GAIN = 25,
    SETTINGS_FIELD_I_GAIN = 26,
    SETTINGS_FIELD_EXTENSION_MODE = 27,
    SETTINGS_FIELD_PIN_MODE = 28,
    SETTINGS_FIELD_BUTTON_MODE = 29,
    SETTINGS_FIELD_SPI_MODE = 30,
    SETTINGS_FIELD_SPI_LATCH_MODE = 31,
    SETTINGS_FIELD_SPI_LATCH_DELAY = 32,
    SETTINGS_FIELD_SPI_CLK_PULSE_LENGTH = 33,
    SETTINGS_FIELD_ADC_MIN_DEAD_ZONE = 34,
    SETTINGS_FIELD_ADC_MAX_DEAD_ZONE = 35,
    SETTINGS_FIELD_ADC_TO_BUTTON_LOW = 36,
    SETTINGS_FIELD_ADC_TO_BUTTON_HIGH = 37,
    SETTINGS_FIELD_ADC_SMOOTHING = 38,
    SETTINGS_FIELD_ADC_INVERT = 39,
    SETTINGS_FIELD_RESET_CENTER_ON_Z0 = 41,
    SETTINGS_FIELD_INTEGRATED_SPRING_STRENGTH = 43,
} SettingsFieldEnum;

typedef enum PinModeEnum {
    PIN_MODE_NONE = 0,
    PIN_MODE_GPIO = 1,
    PIN_MODE_ANALOG = 2,
    PIN_MODE_SPI_CS = 3,
    PIN_MODE_SPI_SCK = 4,
    PIN_MODE_SPI_MISO = 5,
    PIN_MODE_ENABLE_EFFECTS = 6,
    PIN_MODE_CENTER_RESET = 7,
    PIN_MODE_BRAKING_PWM = 8,
    PIN_MODE_EFFECT_LED = 9,
    PIN_MODE_REBOOT = 10,
} PinModeEnum;

typedef enum ButtonModeEnum {
    BUTTON_MODE_NONE = 0,
    BUTTON_MODE_NORMAL = 1,
    BUTTON_MODE_INVERTED = 2,
    BUTTON_MODE_PULSE = 3, // Not implemented
    BUTTON_MODE_PULSE_INVERTED = 4, // Not implemented
} ButtonModeEnum;

typedef enum AmplifierGainEnum {
    AMPLIFIER_GAIN_80 = 0,
    AMPLIFIER_GAIN_40 = 1,
    AMPLIFIER_GAIN_20 = 2,
    AMPLIFIER_GAIN_10 = 3,
} AmplifierGainEnum;

typedef enum SpiModeEnum {
    SPI_MODE_0 = 0, // The first bit is outputted immediately when CS activates. READ-CLK_UP-DELAY-CLK_DOWN-DELAY
    SPI_MODE_1 = 1, // The first bit is outputted on first clock edge after CS activates CLK_UP-DELAY-READ-CLK_DOWN-DELAY
    SPI_MODE_2 = 2, // The first bit is outputted immediately when CS activates. READ-CLK_DOWN-DELAY-CLK_UP-DELAY
    SPI_MODE_3 = 3, // The first bit is outputted on first clock edge after CS activates CLK_DOWN-DELAY-READ-CLK_UP-DELAY
} SpiModeEnum;

typedef enum SpiLatchModeEnum {
    LATCH_MODE_UP = 0, // nCS goes UP for triggering SPI latch
    LATCH_MODE_DOWN = 1 // nCS goes DOWN for triggering SPI latch
} SpiLatchModeEnum;

typedef enum ReportDataEnum {
    DATA_COMMAND_REBOOT = 0x01,
    DATA_COMMAND_SAVE_SETTINGS = 0x02,
    DATA_COMMAND_DFU_MODE = 0x03,
    DATA_OVERRIDE_DATA = 0x10,
    DATA_FIRMWARE_ACTIVATION_DATA = 0x13,
    DATA_SETTINGS_FIELD_DATA = 0x14,
} ReportDataEnum;

typedef enum ReportTypeEnum {
    REPORT_JOYSTICK_INPUT = 0x01,
    REPORT_CREATE_NEW_EFFECT = 0x11,
    REPORT_PID_BLOCK_LOAD = 0x12,
    REPORT_PID_POOL = 0x13,
    REPORT_SET_EFFECT = 0x11,
    REPORT_SET_ENVELOPE = 0x12,
    REPORT_SET_CONDITION = 0x13,
    REPORT_SET_PERIODIC = 0x14,
    REPORT_SET_CONSTANT_FORCE = 0x15,
    REPORT_SET_RAMP_FORCE = 0x16,
    REPORT_EFFECT_OPERATION = 0x1A,
    REPORT_PID_STATE = 0x12,
    REPORT_PID_BLOCK_FREE = 0x1B,
    REPORT_PID_DEVICE_CONTROL = 0x1C,
    REPORT_DEVICE_GAIN = 0x1D,
    REPORT_HARDWARE_SETTINGS_FEATURE = 0x21,
    REPORT_EFFECT_SETTINGS_FEATURE = 0x22,
    REPORT_FIRMWARE_LICENSE_FEATURE = 0x25,
    REPORT_GPIO_SETTINGS_FEATURE = 0xA1,
    REPORT_ADC_SETTINGS_FEATURE = 0xA2,
    REPORT_GENERIC_INPUT_OUTPUT = 0xA3,
} ReportTypeEnum;

typedef struct __attribute__((packed)) {
    float In;
    float Out;
} CurveEntryTypeDef;

typedef struct __attribute__((packed)) {
    CurveEntryTypeDef Values[11];
} CurveTypeDef;

typedef struct __attribute__((packed)) {
    uint16_t RAxisMin[3];
    uint16_t RAxisMax[3];
    uint8_t RAxisSmoothing[3]; // Divide by 100 to get normalized ratio (0..1)
    uint8_t RAxisToButtonLow[3]; // Point in % where button on axis lower value is triggered. If 0 disabled
    uint8_t RAxisToButtonHigh[3]; // Point in % where button on axis upper value is triggered. If 100 disabled
    uint8_t RAxisInvert[3]; // 0 or 1 boolean
    uint8_t _padding[40]; // TODO:IMPORTANT! Keep size 64b. Report size must be same size as in descriptor otherwise Windows will drop the packet as corrupted
} AdcExtensionSettingsTypeDef;

typedef struct __attribute__((packed)) {
    uint8_t ExtensionMode; // See ExtensionModeEnum
    uint8_t PinMode[10]; // See PinModeEnum
    uint8_t ButtonMode[32]; // See ButtonModeEnum
    uint8_t SpiMode; // See SpiModeEnum
    uint8_t SpiLatchMode; // See SpiLatchModeEnum
    uint8_t SpiLatchDelay; // In microseconds
    uint8_t SpiClkPulseLength; // In microseconds
    uint8_t _padding[17]; // TODO:IMPORTANT! Keep size 64b. Report size must be same size as in descriptor otherwise Windows will drop the packet as corrupted
} GpioExtensionSettingsTypeDef;

/**
 * USB report for all generic communication on vendor interface.
 * */
typedef struct __attribute__((packed)) {
    uint8_t ReportId;
    uint8_t Buffer[64];
} HidInOutReportTypeDef;

/**
 * USB report content representing data packet in generic communication report.
 * */
typedef struct __attribute__((packed)) {
    uint8_t ReportData;
    uint8_t Buffer[63];
} DataReportTypeDef;

/**
 * Data representing device type for activation.
 * If serial key passes validation for selected device type device vill be activated in PREMIUM mode.
 * Otherwise device will be activated in LIGHT mode.
 * */
typedef struct __attribute__((packed)) {
    uint8_t DeviceType; // See DeviceTypeEnum
    uint32_t SerialKey[3];
} FirmwareActivationTypeDef;

/**
 * Data representing single settings
 * */
typedef struct __attribute__((packed)) {
    uint8_t Index; // 0 for non indexed settings or index of value in case of array based settings
    uint8_t Buffer[61]; // One of settings value type wrappers
} FieldValueTypeDef;

/**
 * Data representing single setttings fields
 * */
typedef struct __attribute__((packed)) {
    uint8_t FieldId;
    FieldValueTypeDef Value;
} FieldDataTypeDef;

/**
 * Type wrapper for float settings value
 * */
typedef struct __attribute__((packed)) {
    float Value;
} FloatValueWrapperTypeDef;

/**
 * Type wrapper for uint8_t settings value
 * */
typedef struct __attribute__((packed)) {
    uint8_t Value;
} UInt8ValueWrapperTypeDef;

/**
 * Type wrapper for int8_t settings value
 * */
typedef struct __attribute__((packed)) {
    int8_t Value;
} Int8ValueWrapperTypeDef;

/**
 * Type wrapper for uint16_t settings value
 * */
typedef struct __attribute__((packed)) {
    uint16_t Value;
} UInt16ValueWrapperTypeDef;

/**
 * Type wrapper for int16_t settings value
 * */
typedef struct __attribute__((packed)) {
    int16_t Value;
} Int16ValueWrapperTypeDef;

typedef struct __attribute__((packed)) {
    uint8_t ReleaseType; // See FirmwareReleaseTypeEnum for possible types
    uint8_t ReleaseMajor; // Change to the year of the release
    uint8_t ReleaseMinor; // Introduce new version of firmware when new version of companion app is needed
    uint8_t ReleasePatch; // Increment on each patch in scope of the same version
} FirmwareVersionTypeDef;

typedef struct __attribute__((packed)) {
    FirmwareVersionTypeDef FirmwareVersion;
    uint32_t SerialKey[3];
    uint32_t DeviceId[3];
    uint8_t IsRegistered; // Value is 0 or 1 as representation of boolean flag
    uint8_t _padding[35]; // TODO:IMPORTANT! Keep size 64b. Report size must be same size as in descriptor otherwise Windows will drop the packet as corrupted
} FirmwareLicenseTypeDef;

typedef struct __attribute__((packed)) {
    uint16_t MotionRange; // Degrees
    uint16_t StaticDampeningStrength; // 0 to 100 in %.
    uint16_t SoftStopDampeningStrength; // 0 to 100 in %.
    uint8_t TotalEffectStrength; // 0 to 100 in %.
    uint8_t IntegratedSpringStrength; // 0 to 100 in %.
    uint8_t SoftStopRange; // Degrees (will be added on top of MotionRange)
    uint8_t SoftStopStrength; // 0 to 100 in %.
    int8_t DirectXConstantDirection; // -1 or +1
    uint8_t DirectXSpringStrength; // 0 to 100 in %.
    uint8_t DirectXConstantStrength; // 0 to 100 in %.
    uint8_t DirectXPeriodicStrength; // 0 to 100 in %.
    uint8_t _padding[50]; // TODO:IMPORTANT! Keep size 64b. Report size must be same size as in descriptor otherwise Windows will drop the packet as corrupted
} EffectSettingsTypeDef;

typedef struct __attribute__((packed)) {
    uint16_t EncoderCPR;
    uint16_t IntegralGain;
    uint8_t ProportionalGain;
    uint8_t ForceEnabled; // Expect this value to be 0 or 1 as representation of boolean flag
    uint8_t DebugTorque; // Expect this value to be 0 or 1 as representation of boolean flag
    uint8_t AmplifierGain; // See AmplifierGainEnum
    uint8_t CalibrationMagnitude; // 0 to 100 in %.
    uint8_t CalibrationSpeed; // 0 to 100 in %.
    uint8_t PowerLimit; // 0 to 100 in %.
    uint8_t BrakingLimit; // 0 to 100 in %.
    uint8_t PositionSmoothing; // 0 to 100 in %.
    uint8_t SpeedBufferSize;
    int8_t EncoderDirection; // Expect this value to be -1 or +1
    int8_t ForceDirection; // Expect this value to be -1 or +1
    uint8_t PolePairs;
    uint8_t _padding[47]; // TODO:IMPORTANT! Keep size 64b. Report size must be same size as in descriptor otherwise Windows will drop the packet as corrupted
} HardwareSettingsTypeDef;

/**
 * USB report that represent direct control initiated by host side.
 * Device will be constantly listening for this reports on vendor interface.
 * When device do not receive data for extended period of time it will switch to default functioning mode depending on activated device type.
 * */
typedef struct __attribute__((packed)) {

    // Value represents normalized range from -1 to +1 multiplied by 10000 to get 4 fractional digit precision.
    // Min value: -10000
    // Max value: +10000
    // Default value: 0
    int16_t SpringForce;

    // Value represents normalized range from -1 to +1 multiplied by 10000 to get 4 fractional digit precision.
    // Min value: -10000
    // Max value: +10000
    // Default value: 0
    int16_t ConstantForce;

    // Value represents normalized range from -1 to +1 multiplied by 10000 to get 4 fractional digit precision.
    // Min value: -10000
    // Max value: +10000
    // Default value: 0
    int16_t PeriodicForce;

    // Value represents INVERSE ratio normalized range from 0 to +1 multiplied by 100 to get 2 fractional digit precision.
    // Parameter will scale down all forces (DirectX plus Direct control) excluding periodic and dampening.
    // IMPORTANT: TotalForce = InitialForce * (1 - ForceDrop / 100).
    // Min value: 0
    // Max value: +100
    // Default value: 0
    uint8_t ForceDrop;

} DirectControlTypeDef;

/**
 * USB report that represents device state.
 * Device will be constantly sending interrupt report with the state on vendor interface when device is active
 * both for premium and free license.
 */
typedef struct __attribute__((packed)) {

    // Version of firmware that device is running
    FirmwareVersionTypeDef FirmwareVersion;

    // Value is 0 or 1 as representation of boolean flag.
    // Will be determined on the fly for each report.
    uint8_t IsRegistered;

    // Value represents normalized range from -1 to +1 multiplied by 10000 to get 4 fractional digit precision.
    // Min value: -10000
    // Max value: +10000
    int16_t Position;

    // Value represents normalized range from -1 to +1 multiplied by 10000 to get 4 fractional digit precision.
    // Min value: -10000
    // Max value: +10000
    int16_t Torque;

    // TODO:IMPORTANT! Keep size 64b. Report size must be same size as in descriptor otherwise Windows will drop the packet as corrupted
    uint8_t _padding[55];

} DeviceStateTypeDef;

```

FFBeast wheel is a combined interface. Interface 0 is custom HID. Interface 1 is standard Joystick HID. All custom communication is done with interface 0.
To obtain device connections with hidapi you can use next code snippet:


### Obtaining custom interface device handle

```C
hid_device * obtainDeviceConnection(){
    struct hid_device_info *devs, *cur_dev;
    const char *path_to_open = nullptr;
    hid_device * handle = nullptr;
    devs = hid_enumerate(1115, 22999); // Wheel VID and PID
    cur_dev = devs;
    
    while (cur_dev) {
        if (cur_dev->interface_number == 0){ //Vendor interface is 0 
            path_to_open = cur_dev->path;
            break;
        }   
        cur_dev = cur_dev->next;
    }
    
    if (path_to_open) {
        handle = hid_open_path(path_to_open);
    }
    
    hid_free_enumeration(devs);
    
    return handle;
}
```

When device connection is established you can perform communication. Here are couple of examples.

### Read device state

Device state is constantly reported by device so it can be read just with hid read method.

```c
DeviceStateTypeDef readState(DeviceStateTypeDef *state, hid_device *handle){
    unsigned char readBuffer[65] = {};
    DeviceStateTypeDef state;
    int result = hid_read_timeout(handle, readBuffer, 65, 100);
    memcpy(&state,(DeviceStateTypeDef *)(&readBuffer[1]),sizeof(DeviceStateTypeDef));
    return result;
}
```

### Read effect settings

Settings on other hand are read with get feature report. This principle can be applied to other reports:

- REPORT_HARDWARE_SETTINGS_FEATURE
- REPORT_EFFECT_SETTINGS_FEATURE
- REPORT_FIRMWARE_LICENSE_FEATURE
- REPORT_GPIO_SETTINGS_FEATURE
- REPORT_ADC_SETTINGS_FEATURE

```c
EffectSettingsReportTypeDef readEffectSettings(){
    EffectSettingsReportTypeDef effectSettingsReport;
    effectSettingsReport.ReportId = REPORT_EFFECT_SETTINGS_FEATURE;
    hid_get_feature_report(handle, (unsigned char*)&effectSettingsReport, sizeof(EffectSettingsReportTypeDef));
    return effectSettingsReport;
}
```

### Reboot command

Commands can be sent to device with norma hid write methods. Other commands supported:

- DATA_COMMAND_REBOOT
- DATA_COMMAND_SAVE_SETTINGS
- DATA_COMMAND_DFU_MODE

```c
void rebootControllerRequest(){
    HidInOutReportTypeDef genericReport = {};
    genericReport.ReportId = REPORT_GENERIC_INPUT_OUTPUT;
    DataReportTypeDef *data = (DataReportTypeDef*)&genericReport.Buffer;
    data->ReportData = DATA_COMMAND_REBOOT;
    hid_write(handle, (const unsigned char *) &genericReport, 65);
}
```

### Change setting

Same principle is applied to settings wrapped into uin8, uint16, int8, int16, float values.

```c
void sendUInt8SettingReport(SettingsFieldEnum field, int8_t index, uint8_t data){
    HidInOutReportTypeDef genericReport = {};        
    genericReport->ReportId = REPORT_GENERIC_INPUT_OUTPUT;
    DataReportTypeDef *genericData = (DataReportTypeDef *) &genericReport->Buffer;
    genericData->ReportData = DATA_SETTINGS_FIELD_DATA;
    FieldDataTypeDef *settingsFieldData = (FieldDataTypeDef *) &genericData->Buffer;
    settingsFieldData->FieldId = fieldId;
    FieldValueTypeDef *settingsField = &settingsFieldData->Value;
    settingsField->Index = index;
    UInt8ValueWrapperTypeDef *valueWrapper = (UInt8ValueWrapperTypeDef *) &settingsField->Buffer;
    valueWrapper->Value = value;    
    hid_write(handle, (const unsigned char *) &genericReport, 65);
}
```

### Send direct control

This approach can be used for buffer reports:

- DATA_OVERRIDE_DATA
- DATA_FIRMWARE_ACTIVATION_DATA

```c
void sendUInt8SettingReport(DirectControlTypeDef control){
    report->ReportId = REPORT_GENERIC_INPUT_OUTPUT;
    DataReportTypeDef *genericData = (DataReportTypeDef *) &report->Buffer;
    genericData->ReportData = DATA_OVERRIDE_DATA;
    memcpy(genericData->Buffer,&control,sizeof(DirectControlTypeDef));
    hid_write(handle, (const unsigned char *) &genericReport, 65);
```