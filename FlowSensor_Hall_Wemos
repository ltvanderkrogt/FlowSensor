// based on: https://lastminuteengineers.com/handling-esp8266-gpio-interrupts-tutorial/?utm_content=cmp-true
// improved by: https://chat.openai.com/chat 
// source: https://github.com/ltvanderkrogt/FlowSensor 

struct FlowMeter {
  const uint8_t PIN;
  float pulsesPerLitre;
  float flowRate;
  unsigned int flowArray[100];
  unsigned int flowIndex;
};

FlowMeter flowMeter = {D5, 7.7, 0.0, {0}, 0}; // 7,7 pulses per liter 

//variables to keep track of the timing of recent interrupts
unsigned long trigger_time = 0;
unsigned long last_trigger_time = 0;

void ICACHE_RAM_ATTR isr() {
  trigger_time = micros();
  if (trigger_time - last_trigger_time >= 1000)
  {
    flowMeter.flowArray[flowMeter.flowIndex++] = trigger_time - last_trigger_time;
    if (flowMeter.flowIndex >= 100) {
      flowMeter.flowIndex = 0;
    }
    last_trigger_time = trigger_time;
  }
}

void setup() {
  Serial.begin(115200);
  pinMode(flowMeter.PIN, INPUT_PULLUP);
  attachInterrupt(flowMeter.PIN, isr, FALLING);
}

void loop() {
  float totalTime = 0.0;
  for (int i = 0; i < 100; i++) {
    totalTime += flowMeter.flowArray[i];
  }
  float averageTime = totalTime / 100.0;
  float averageFrequency = 1000000.0 / averageTime;
  flowMeter.flowRate = averageFrequency / flowMeter.pulsesPerLitre;
  Serial.printf("Flow rate: %.2f L/min\n", flowMeter.flowRate);
}
