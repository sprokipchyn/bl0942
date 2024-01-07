# bl0942

Modified component for ESPHOME, compatible with LibreTiny. Added waiting for the full data package to be received. Optimized the time of publication of sensors.

### Usage example
```yaml
external_components:
  - source:
      type: git
      url: https://github.com/sprokipchyn/bl0942
    components: [bl0942]
  
uart:
  id: uart_bus
  tx_pin: P11
  rx_pin: P10
  baud_rate: 4800
  data_bits: 8
  stop_bits: 1

sensor:
  - platform: bl0942
    uart_id: uart_bus
    voltage:
      name: "Voltage"
    current:
      name: "Current"
    power:
      name: "Power"
    energy:
      name: "Energy"
    frequency:
      name: "Frequency"
      accuracy_decimals: 2
    update_interval: 1s
```
