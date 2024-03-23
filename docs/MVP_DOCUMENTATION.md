# MVP Documentation

## MVP 1: Initial Release with 2kHz Fundamental Frequency

### Release Date
- March 21, 2024

### Objectives
- Achieve a fundamental frequency of 2 kHz.
- Implement a switching frequency of 12 kHz.
- Deliver the solution in a binary format for direct burning.

### Achievements
- Successfully developed and delivered the first MVP that meets the fundamental and switching frequency requirements.
- Provided the solution in `.bin` format as requested by the customer.

### Customer Feedback
- The system operates as expected for 3 to 4 seconds after reset and pressing User SW1 but then stops.
- Suspected issue related to current sensing that prevents continuous operation.

### Action Items
- Investigate the potential issue related to current sensing.
- Implement a fix to ensure continuous operation of the system.
- Update the binary file with the resolved version for customer testing.

## MVP 2: Enhanced Current Sensing and Motor Inverter Board Configuration

### Release Date
- March 23, 2024

### Objectives
- Improve the system's stability and performance by configuring the motor inverter board for enhanced current sensing.
- Utilize three shunt resistors for accurate current measurement.
- Introduce adjustments in the microcontroller's GPIO configuration to manage current sensing and system modes more effectively.
- Optimize the potentiometer reading for better control precision.

### Achievements
- **Motor Inverter Board Configuration:** Configured the motor inverter board for current sensing with three shunt resistors, aiming for improved accuracy in current measurement and overall system stability.
- **GPIO Configuration Adjustments:**
  - Set PA3, PA4, and PA5 to RESET_STATE to disable current sensing temporarily, enhancing system control during specific operational modes.
  - Based on the STSPIN32F0 documentation and the "Overcurrent Protection Application Note" (AN4999), set PF6 and PF7 to LOW to put the system into standby mode, conserving power and resources when not in active use.
- **ADC Configuration for Potentiometer:** Configured ADC_IN6 (PA6) to read the potentiometer output (Trimmer) with a sampling time of 2us and a 28.5 ADC clock cycle, ensuring precise control over the system's operations based on user input.

### Technical Details and References
- The adjustments to the GPIO and ADC settings are based on detailed specifications and recommendations found in the STSPIN32F0 series documentation and the application note on overcurrent protection. For more details, refer to the [STSPIN32F0F0AF0B Overcurrent Protection Application Note](https://github.com/aabdelghani/TriSineWaveGenerator/blob/main/docs/boardsDocs/STSPIN32F0F0AF0B%20overcurrent%20protection%20AN4999%20Application%20Note.pdf), specifically the table on page 3.

### Customer Feedback
- *sent and still waiting for his feedback*
  
### Action Items
- *On hold based on customer feedback*
