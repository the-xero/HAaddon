Homeassistant addons
====================
### kimtc99님의 코맥스 월패드 애드온의 paho-mqtt 버전 업데이트에 따른 오류 수정 포크입니다.
`ValueError: Unsupported callback API version: version 2.0 added a callback_api_version, see migrations.md for details`

HAOS 버전업에 따라 paho.mqtt.python 2.0 업데이트 후 commax-mqtt2elfin 애드온에서 제대로 동작하지 않는 부분 수정을 위한 포크

```
#수정 전
    mqtt_client = mqtt.Client('mqtt2elfin-commax')
# 수정 후
    mqtt_client = mqtt.Client(mqtt.CallbackAPIVersion.VERSION1, 'mqtt2elfin-commax')
```

근본적인 수정은 아니므로 추후 하위버전 지원에 따라 동작을 하지 않을 수 있습니다. 
아래는 기존 사람님 저장소 링크입니다.

## 코맥스 월패드 애드온 - socket 전용
### [commax-mqtt2elfin](https://github.com/kimtc99/HAaddon/tree/master/commax-mqtt2elfin) (추천)
socket 통신을 없애고 모두 mqtt를 사용합니다. python3를 이용하여 작동합니다.
이 방법을 추천합니다.
