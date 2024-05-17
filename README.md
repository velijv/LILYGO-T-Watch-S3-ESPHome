# LILYGO® <img alt="LILYGO" src="static/logos/lilygo-favicon.svg" height="28"> T-Watch S3 <img alt="ESPHome" src="static/logos/esphome-favicon.svg" height="28">  ESPHome

LILYGO®  T-Watch S3 full feature implementation for ESPHome

## T-Watch S3 ESPHome


### Specs

<details>
<summary>Technical details 🧑‍💻 + <a href="static/datasheets">datasheets 📚 </a></summary>


> Espressif Systems ESP32-S3 (revision v0.2) dual-core Tensilica LX7 @ up to 240 MHz with vector instructions for AI acceleration
> * Bluetooth: BLE V5.0
> * Multiprotocol Modules SMD Module, ESP32-S3R8, 3.3V,
> * 8 MB Octal PSRAM Die (OPI)
> * 16 MB Quad SPI Flash, (QIO) Quad I/O  4 pins used for address & data.
> * 512KB SRAM
> * 128-bit data bus and SIMD commands
> * 384 KB ROM
> * 16 KB SRAM in RTC
> * CONNECTOR (OK-22F024-04) - terminal board-to-board connector

![Watch](static/images/t-watch-s3-esp32-s3-lora-transparent.png "T-Watch")
</details>

<!--
<details open>
<summary> <h3>T-Watch S3 ⌚️</h3> </summary>
</details>
-->

### Result

<table>
	<thead>
		<tr>
			<th><img src="https://img.shields.io/badge/LILYGO-f5a012.svg?logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGZpbGw9Im5vbmUiIHZpZXdCb3g9IjAgMCAyNCAyNCI+CiAgPGcgY2xpcC1wYXRoPSJ1cmwoI2EpIj4KICAgIDxwYXRoIGZpbGw9IiNGNUEwMTIiIGZpbGwtcnVsZT0iZXZlbm9kZCIgZD0ibTE3LjYuMy0uNi42YzAgLjMtLjMuNC0xIC40LTEgLjEtMS41LjUtMS44IDEuMi0uMi40LS4zLjUtLjYuNGgtMS4xYy0uNiAwLTEtLjEtMS0uMy0uNS0uNS0xLjctLjItMi41LjctLjQuNS0xLjEgMS41LTEuMSAxLjdsLjQuMmMuNC4xLjQuMS4yLjYtLjMuNC0uNC41LTEgLjUtMS4zIDAtMS40IDEtLjIgMSAuNi4xLjYuMS42LjggMCAuNi42IDIuNC45IDIuNGwuNy4zYy42LjUgMS44LjggMi4zLjcuMy0uMS4zIDAgLjMgMXMwIDEtLjQgMWMtLjYgMC0xLjYuNS0yLjIgMUw5IDE1bC0xLjQtLjRhMTEgMTEgMCAwIDAtMi0uNWwtMS44LS4zYy0xLS4yLTEuMi0uNC0xLjMtLjdsLS4yLTIuNi0uMS0yLjljMC0uNiAwLS42LjQtLjguNS0uMS41LS4yLjYtLjcgMC0uNiAwLS42LS41LS44QzIgNSAyIDQuOSAyLjMgMy44Yy4zLTEgLjQtMS45IDAtMS45LS4yIDAtLjQuNS0uNCAxLjJzLS4yLjQtLjYtLjhDLjcuNCAwIC4xIDAgMS43YzAgMSAuNCAyLjMuOSAyLjhsLjQuNS0uNi4zYy0uNS4yLS42LjItLjUuOCAwIC41LjEuNi42LjcuNi4yLjYuMy43IDQgLjEgMy4zIDAgMy4zIDIgMy44LjkuMiAxLjYuNSAxLjcuNmwxLjMuNGMxLjMuMiAyIC40IDEuOC42bC0uMiAxYy0uNCAxLjYuNCAzIDIgMy44bC45LjR2Mi4zaDMuNWwtLjItLjdjLS4zLTEuNC0uMi0xLjUuNy0yYTQgNCAwIDAgMCAyLjEtMi4ybC4yLTFzLjQuMSAxIC42bDEgLjggMS44IDEgMiAxLjNjLjQgMCAuOS0uMy45LS42IDAtLjItMS0xLjItMi4yLTIuNC0yLTItMi41LTIuNS0xLjctMi4xLjYuMy44LjIgMS4yLS41LjYtLjkgMi43LTUuNCAyLjctNS44IDAtLjEtLjItLjQtLjUtLjZsLTQuNC0yYy0uMiAwLS41LjQtLjcuOC0uNiAxLTIuNSA1LjMtMi41IDUuOHMwIC40LS42LjFsLTEuNC0uNC0uOC0uMnYtMWwtLjItMS4xYzAtLjIgMS4yLTEuMiAxLjktMS41LjctLjQgMi0zLjEgMi00LjMtLjEtLjctLjEtLjguNC0xIC4zIDAgLjYtLjIuOC0uNGEyIDIgMCAwIDAgMC0xLjdjLS4xLS4zIDAtLjQuNS0uNy44LS41IDEuMi0xLjEuNy0xLjYtLjMtLjQtMS0uNC0xLjYgMFpNMTIgNS4xdjEuM2MwIDItLjggMi44LTIgMi4zLS44LS4zLTEtLjYtMS0xLjUgMC0xLjMuNy0yLjEgMS4zLTEuNS4zLjMuMyAxLjYgMCAyLjItLjIuNCAwIC43LjQuNi41LS4yLjgtMSAuOC0ydi0xaC0xLjNsLTEtLjEtLjUuN2E0IDQgMCAwIDAtLjMgMi44Yy4yLjcuNC44IDEgLjUuMy0uMS4zLS4xIDAgLjMtLjMuNS0uMy41IDAgLjcgMS4zIDEgMyAuOSA0LjUtLjNsLjUtLjQtLjgtMS41TDEyIDV2LjFabS0xMC43LjcuMy4yYy4xIDAgLjIgMCAuMi4yIDAgLjEtLjEuMi0uMi4xbC0uMi4xLjYuMmMuNSAwIC42IDAgLjYtLjRzLS41LS43LTEtLjdjLS40IDAtLjUgMC0uMy4zWm01LjYuOWMtLjIuMiAwIC40LjYuNC40IDAgLjYtLjEuNi0uMyAwLS4xLS4yLS4yLS42LS4ySDdsLS4xLjFaTTE4LjUgOWMtLjcgMS4zLTIuMiA0LjgtMi4yIDUgMCAuMi4zLjQuOC42IDEgLjQgMSAuNC44LjEgMCAwLS4yLS4yLS4zLS4xLS4yIDAtLjIgMCAwLS40bC4yLS42LS4yLjRjLS4yLjUtLjYuNi0uOC4zIDAtLjIuMy0xLjEuNS0xLjF2LjJjLS4xLjIgMCAuMS43LS4xbC42LS4yLS40LS4xYy0uMyAwLS41LS4yLS41LS4zIDAtLjQuNy0xLjYgMS0xLjYgMCAwIC4yLS4xLjItLjMuMS0uMi4zLS4zLjQtLjIuMi4xLjIuMiAwIC42LS4zLjYtLjQuOS0uMi45bC43LTEuM2MuNC0xIC42LTEuMy44LTEuMi4yIDAgLjMgMCAuNC0uMy4xLS4yLjMtLjIuNC0uMS4yIDAgMCAuNC0uNSAxLjdhMjYgMjYgMCAwIDAtLjggMS43bC4zLjFjLjIgMCAuMiAwIC4xLjNsLS4yLjZjMCAuMy0uMS4zLS42IDBsLS42LS4yLjQuOGMuMSAwIC4yLjEuMS4yIDAgLjUgMCAuNi4zLjMuMS0uMy4yLS40LjMtLjJ2LjVjLS4yLjEtLjIuMy0uMi40bC4yLS4zYy4zLS41LjYtLjYuNi0uM2wtLjMuN2MtLjIuNC0uMy40LS41LjMgMC0uMi0uMi0uMi0uMiAwbC42LjMuMy0uNmMuMS0uMy4zLS41LjQtLjVsLS4yLjYtLjIuN2MuMiAwIDMtNi4xIDMtNi4zbC00LTEuOC0uNy0uMy0uNSAxVjlabTEuNyAxLjN2LjJjLjIgMCAuMy0uMS4zLS4ybC0uMS0uMi0uMi4yWk0yMCAxM2MwIC4xIDAgLjIuMS4xbC4yLS4yaC0uMmMtLjIgMC0uMSAwLS4xLjFabS0zLjQuN2MtLjIuMy0uMi41IDAgLjRsLjItLjctLjIuM1ptLS4xIDEuNC42IDFjLjIuNS40LjggMS4zIDEuM2wyLjMgMS40Yy4yLS4yLTEuNC0xLjgtMS45LTJhLjkuOSAwIDAgMS0uNS0uN2MtLjEtLjQtLjMtLjYtMS0xbC0xLjEtLjVzMCAuMy4zLjVaIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiLz4KICA8L2c+CiAgPGRlZnM+CiAgICA8Y2xpcFBhdGggaWQ9ImEiPgogICAgICA8cGF0aCBmaWxsPSIjZmZmIiBkPSJNMCAwaDI0djI0SDB6Ii8+CiAgICA8L2NsaXBQYXRoPgogIDwvZGVmcz4KPC9zdmc+Cg==&logoColor=fff&labelColor=rgba(0,0,0,0)&color=rgba(245,160,18,0.1)&style=flat-square">
			<img src="https://img.shields.io/badge/ESP32S3%20N16R8V-e7352c.svg?logo=Espressif&logoColor=e7352c&labelColor=rgba(0,0,0,0)&color=rgba(231,53,44,0.1)&style=flat-square">
			</th>
			<th>
				<img src="https://img.shields.io/badge/ESPHome-000?logo=Esphome&logoColor=808080&labelColor=rgba(0,0,0,0)&color=rgba(33,33,33,0.1)&style=flat-square">
				<img src="https://img.shields.io/badge/Home%20Assistant-03A9F4?logo=HomeAssistant&logoColor=1abcf2&labelColor=rgba(0,0,0,0)&color=rgba(26,188,242,0.1)&style=flat-square">
			</th>
			<th>
				<a href="https://veli.ee/sponsor">
					<img src="https://img.shields.io/badge/Veli-f5a012.svg?logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGZpbGw9Im5vbmUiIHZpZXdCb3g9IjAgMCA1MTIgNTEyIj4KICA8Y2lyY2xlIGN4PSIyNTYiIGN5PSIyNTYiIHI9IjI1MSIgc3Ryb2tlPSIjMDBGIiBzdHJva2Utd2lkdGg9IjEwIi8+CiAgPHBhdGggZmlsbD0iIzAwRiIgZD0iTTI1NiA1MTJjLTI0IDAtNDYtMy02OC05LTYtMTMtMTgtMjYtMjYtMzctOS0xMi0yMS0yNi0yNC0zLTEgMyAxIDEyIDIgMjFsLTYtM2MxLTgtMS0xOC0yLTIzIDAtMzIgMC02MC0xMC05MS01LTE1LTIxLTE3LTI2LTMzLTQtMTMtMy0yOC01LTQxLTItMTItMTUtNDUtMy01MSA5LTUgMTMgNyAyMSA5di0zMWMwLTE2LTUtMzEtNC00NyAyLTE1IDctMjggMTEtNDMgNS0xNyA3LTM0IDE2LTUwIDE0LTI2IDM2LTQyIDYzLTUwbDE5LTVjOC0xIDExIDIgMTcgMyA0IDIgMTEgMiAxNyAyLTMtMS0xOS0xLTExLTcgMy0yIDExLTIgMTUtMiAxMyAwIDI2LTEgMzggMiAyNSA2IDQ2IDIyIDYzIDM5IDQgNCA2IDEwIDkgMTNsNyAyYzkgMTEgMTEgMjUgMTggMzggNSA5IDEzIDI0IDE0IDM0bC0yIDE1IDQgMjhjMSAxMiA1IDMzIDAgNDUtNyAxNi0xOSAxMS0yOSA1LTEzLTgtMjUtMTUtMzgtMjAtOS00LTEwLTQtMTgtMy02IDEtMTEgNC0xNyAzLTEyLTEtMTEtNC0xNS05bC0zIDFjLTktNSAyNS05IDI0LTloMjRjMTEgMSAyNiAyIDMzIDEwIDcgNyAxMiAyNSAyNCAyNSAxNyAwIDQtOCAwLTEyLTIgMC05LTgtOC0xMCAwLTIgNy0zIDktNyAzLTktNi0yMC05LTI3LTItNi05LTMwIDMtMjMtNC04IDMtNyAzLTEzIDAtNy03LTE5LTEwLTI1YTgyIDgyIDAgMCAwLTYxLTQ2Yy0yNC0zLTQ2LTMtNzEtMS0xOSAyLTM4IDYtNDUgMjctNCAxMC0xIDE2IDUgMjUgMiAyIDEwIDkgNyAxMnMtMTktNy0yMi04Yy02LTItMy01LTktMy02IDEtMTAgMTItMTIgMTctMyAxMSA0IDE5IDIgMjktMSA2LTExIDEyLTYgMTggMyA0IDctMTEgMTUtNSA1IDMtMSAyIDAgNCA0IDYtMiA0IDUgMTAgNiA2IDEwIDUgMTggNmw3IDJjMTIgMyAxMiAzIDE1IDE2IDMgMTEgMTMgMTkgMTUgMjkgMiA4LTIgMTItNCAyMi0xIDEwLTUgMTktNyAyOS0zIDExIDUgMjUgMTggMjEgOS0yIDgtMTIgMjAtN3M4IDE0LTIgMTdjMy0xLTctMi04LTEtMTEgMS0yMCAzLTMyIDEtOS0yLTE1LTQtMTAtMTQgMC0yIDE1LTcgNC04LTE0LTEtMTIgMTktNyAyNiAzIDQgMjAgOSAyMSAxNSAxIDgtMTQgMTQtMTUgMjItMiA4IDI3IDUgMzYgNSA2IDAgMTIgMiAxNyAzbDE1IDFjNiAxIDE4IDMgMTcgMTAtMSA5LTI5IDExLTM1IDExLTkgMS0yOC0zLTM2IDMgMyA3IDIzIDAgMjggMSA3IDAgNy0xIDExIDMgMSAwIDggOCA3IDktMSA2LTU0IDEwLTYxIDEzLTMxIDEyLTEgMTcgMTMgMjMgMyAyIDYgNiA5IDcgNSAxIDEzLTQgMTctNSAxMi0zIDI2LTQgMzUtMTEgOS02IDE1LTE4IDIxLTI2IDMtNSAxNC0xNCAxNC0xNiAwLTQtMTUtMTUtNy0yMCA2LTMgNiA4IDExIDAgMi0yLTEtMTIgNy0xMyA1LTEgOSAzIDcgMTAtMSAzLTUgNC01IDUtMiA1LTEgNS0xIDEwIDAgMTIgNCAyMC00IDMwLTYgNy0xNyAxMi0yNCAxOGwtMyA1LTYgMWMtMyA0LTUgNC02IDEwIDIgMiAyMy0xMiAyNy0xNSAxNS04IDIyLTE4IDI3LTMzIDExLTI4IDExLTYwIDI1LTg3IDMtNyAxMC0xMiAxMy0yMCAyLTYgMC0xMSAyLTE3bDQtMTFjMy0xIDUtMyA1LTZsLTItMTNjMy0xOCAzIDQgNiA2IDUgNCA5IDAgOS02IDEtNy0zLTQtNC04LTEtNiAzNC0yNyAzMCA2LTEgNSAwIDEyLTIgMTVsLTItNWMtMSA0LTkgMTEtNCAxNmw1LTdjLTIgMTEtMyAyMi03IDMyLTEgMi05IDE3LTExIDhsNy04YzItNSAzLTEyIDEtMTctMy0xMi0yLTUtOS01bC02IDNjLTEgMS01LTQtNy0yLTYgNCAwIDE0IDQgMTcgNSA1IDExLTEgNiA3LTUgNy0xMSA1LTE0IDE1bC0xIDExczAgMTUgMiAxM2MtMiA0LTcgMy0xMCA3LTEwIDE2LTExIDQ5LTEzIDY3bC0xIDI5YzAgNi0zIDE4LTEgMjdsLTExIDUgMS0xMmMwLTggNy0zMC03LTIyLTUgMi04IDEyLTExIDE2bC0xNCAxNi0xMCAxN005OSAzMjNzLTEgNiAyIDQtMS02LTItNFptNi02MmMtMS04LTctNi0xMy01IDMgNCAxMyAxOSAxMyA1Wm0zIDY1LTMtM2MwIDEgMSA0IDMgM1ptNDktOTBjNyAwIDE1LTMgMjItNCAxMS0xIDI4IDcgMzYgMi0xMC0xMC0zNi0xMS01MC0xMi0xMyAwLTI3IDEzLTggMTRabTM2IDktMyA0YzMgMSA1IDEgNi0ybC0zLTJabS0zOS0zYzEtMSAzMC01IDMyLTQtNC04LTMxIDItMzIgNFptMjkgMTYzYzQtNSA0LTEyIDgtMTdsNS02YzEtMyA0LTQgMS05LTEtMi01IDMtNSAyLTItNS0zLTEgMy03IDMtMyAyMC0xNSAxOC0yMC0xLTMtMTAtMy0xMS03LTItMyAxLTUgMS05IDAtNSAxLTExIDMtMTYgMy05IDEyLTE1IDE0LTIzIDMtNiAwLTctMy0xM2wyLTVjLTItMy01IDUtNSA1LTMtMyAzLTExIDMtMTEtNS02LTcgNS0xMSAyLTQtMiAxLTggMS05IDMtMyA4LTEgMTAtNyAyLTctMi03LTctMTAgNCAxMS0zIDgtMTMgOWwtNDEgNmMtMSAzIDcgNSA2IDhsLTExIDZjLTE3IDExLTIyIDEyLTE1IDMzbDcgMjZjMiA3IDcgMTAgMTAgMTYgNSAxMS0xIDIxIDggMzIgMyAzIDUtMSA4IDEgMyAxIDIgNCAzIDcgNiA4IDUgMjUgMTIgMzIgNSA1IDE4IDUgMTgtMyAxLTEwLTEzLTE0LTE5LTEzWm05OS0xNTZjLTIgNS0xIDMgMyA0IDkgMSA5LTUgMTQtOGwxMCA4YzUgMyA4IDIgMTEgM2wyMyAzYzE2IDAgMjMtNyA3LTE2LTktNS0yMC0xMC0zMC05IDIgNCAxMyAzIDEzIDcgMCAxLTIwLTQtMjQtMy00IDAtMjYgOC0yNyAxMVptNy0xMWM3LTEgMjAtMSAyNS01LTgtMS0yMS0zLTI1IDVaIi8+Cjwvc3ZnPgo=&logoColor=fff&labelColor=rgba(0,0,0,0)&color=rgba(0,0,255,0.1)&style=flat-square">
				</a>
				</th>
		</tr>
	</thead>
	<tbody>
	<tr>
		<td> <img src="static/icons/tech.svg" alt="T-Watch S3" width=256 height=256> </td>
		<td> <img src="static/icons/watch.svg" alt="T-Watch S3" width=256 height=256> </td>
		<!--td> <img src="static/icons/branded.svg" alt="T-Watch S3" width=256 width=256> </td-->
		<td> <img src="static/icons/veli.svg" alt="T-Watch S3" width=256 width=256> </td>
	</tr>
	</tbody>
</table>






## Features

> [!TIP]
> Use all the devices capabilities that it is supposed to do with factory software.

#### Microphone
<details>
  <summary> 🎙️ (SPM1423HM4H-B PDM) <code>yaml</code> 👇 </summary>

```yaml
microphone:
  - platform: i2s_audio
    bits_per_sample: 16bit
    channel: right
    i2s_din_pin: ${BOARD_MIC_DATA}
    adc_type: external
    pdm: true
```
</details>


<table>
	<tr>
		<td><img alt="" src="static/screen_server/audio.bmp"></td>
		<td><img alt="" src="static/screen_server/audio-waveform.bmp"></td>
		<td><img alt="" src="static/screen_server/audio-rtp.bmp"></td>
	</tr>
</table>


#### Speaker
<details>
  <summary> 🔊 (MAX98357A) with R0805 speaker <code>yaml</code> 👇 </summary>

```yaml
media_player:
  - platform: i2s_audio
    i2s_dout_pin:
      number: ${BOARD_DAC_IIS_DOUT}
      ignore_strapping_warning: true
    dac_type: external
    mode: mono
    i2s_comm_fmt: msb
```
</details>

- [x] `voice_assistant` enabled

<table>
	<tr>
		<td><img alt="" src="static/screen_server/va-passive.bmp"></td>
		<td><img alt="" src="static/screen_server/va-ok.bmp"></td>
		<td><img alt="" src="static/screen_server/va-error.bmp"></td>
	</tr>
<table>



#### ST7789V

<details>
  <summary> 📺 Display (ST7789V) 240x240 220ppi 16-bit, 1.54" IPS LCD over SPI <code>yaml</code> 👇 </summary>

```yaml
display:
  - platform: ili9xxx
    model: ST7789V
    transform:
      mirror_x: true
      mirror_y: true
      swap_xy: false
    dimensions:
      width: ${BOARD_TFT_WIDTH}
      height: ${BOARD_TFT_HEIGHT}
      offset_width: 0
      offset_height: 80
    invert_colors: true
    cs_pin: ${BOARD_TFT_CS}
    dc_pin: ${BOARD_TFT_DC}
```
</details>

#### FT6336
<details>
  <summary> 🫵 Touchscreen (FT63X6/FT6336) Capacitative touch Wide angle TFT LCD Display <code>yaml</code> 👇 </summary>

```yaml
touchscreen:
  - platform: ft63x6
    id: ft6336
    i2c_id: touch_bus
    address: 0x38
    interrupt_pin:
      number: ${BOARD_TOUCH_INT}
```
</details>

- [x] Use `interrupt_pin` to wake from `deep_sleep`
- [x] Custom code to recognise swipe gestures!

#### PCF8563
<details>
  <summary> 🕰️ RTC Clock (PCF8563 + battery) <code>yaml</code> 👇 </summary>

```yaml
time:
  - platform: pcf8563
    id: rtc_time
    i2c_id: primary_bus
    address: 0x51
#    interrupt_pin:
#      number: ${BOARD_RTC_INT_PIN}
```
</details>

- [ ] Add `interrupt_pin` functionality to allow waking from `deep_sleep`

#### <code>remote_transmitter</code>
<details>
  <summary> 🟣 Infrared (IR) <code>yaml</code> 👇 </summary>

```yaml
remote_transmitter:
  pin:
    number: ${BOARD_IR_PIN}
  carrier_duty_percent: 50%
```
</details>

- [x] dynamic implementation to send *any* `remote_transmitter` protocol from one `text` input
- [x] **ESPHome** implementation of **[tv-b-gone](https://github.com/search?q=tv-b-gone)**



## Custom Components


<table>
	<thead>
		<tr>
			<th>Battery Charger</th>
			<th>Touch Grid</th>
			<th>Sensor Test</th>
		</tr>
	</thead>
	<tbody>
	<tr>
		<td><img alt="" src="static/screen_server/battery.bmp"></td>
		<td><img alt="" src="static/screen_server/sensors.bmp"></td>
		<td><img alt="" src="static/screen_server/gyro.bmp"></td>
	</tr>
	</tbody>
</table>

<details open>
  <summary> custom 🦄 components for</summary>

<!--
```yaml
external_components:
  - source: components
    components: [ drv2605 ]

  - source: components
    components: [ axp2101 ]

  - source: components
    components: [ bma423 ]
```
-->

### AXP2101

<details open>
  <summary> 🔋 PMU (Highly Integrated Power Management Unit) </summary>

- [x]  manager your own power, set low power warning
- [x]  Access button presses
- [x]  disable/enable power for any integrated component

<details>
  <summary><code>yaml</code></summary>

```yaml
  - platform: axp2101
    model: TWATCHS3
    address: 0x34
    interrupt_pin:
      number: ${BOARD_PMU_INT}
    short_press:
      name: Short Press
    long_press:
      name: Long Press
    battery_powercut:
      name: Battery Powercut
      device_class: voltage
    battery_voltage:
      name: Battery Voltage
      device_class: voltage
    battery_level:
      name: Battery Level
      device_class: battery
    battery_charging:
      name: Battery Charging
    connectivity:
      name: USB Plugged
      device_class: plug
```
</details>

</details>

### BMA423

<details open>
  <summary> 🧭 Gyroscope/Pedometer (BMA423 3-axis Accelerometer)</summary>

- [x] Step Counter, Interaction recognition
- [x] Wake the display by tapping on the display
- [x] Use `interrupt_pin` to wake from `deep_sleep`

<details>
  <summary><code>yaml</code></summary>

```yaml
bma423:
  address: 0x19
  interrupt_pin:
    number: ${BOARD_BMA423_INT1}
  orientation:
    name: Orientation
  temperature:
    name: Internal Temperature
  steps:
    name: Steps
  acceleration_x:
    name: X
  acceleration_y:
    name: Y
  acceleration_z:
    name: Z
  tilt:
    name: Tilt
  wakeup:
    name: Wakeup
  step_counter:
    name: Step Counter
  activity:
    name: Activity
  no_motion:
    name: No Motion
  any_motion:
    name: Any Motion
```
</details>

</details>





### DRV2605L

<details open>
  <summary> 📳 Haptics (Haptic Driver Motor for ERM and LRA with Effect Library and Smart-Loop Architecture) </summary>

- [x] use 127 ready-make vibration effects multiplied by 6 modes
- [x] Use your microphone or speaker to generate real-time haptic feedback
- [x] draw waveforms on your display

<details>
  <summary><code>yaml</code></summary>

```yaml
drv2605:
  address: 0x5a
```

</details>

</details>

### SX1262

<details open>
  <summary>  📻 LoRa (Semtech SX1262)  </summary>

- [ ] Semtech SX1262 LoRa RF transceiver: 433 MHz, 868 MHz, 915 MHz
- [ ]  SX1262 Low Power Transceiver (Support Baud: 433Mhz, 868Mhz, 915Mhz)

</details>

</details>



## Pre-made `display` `pages`

### Global
> `graphical_display_menu` `esp32_improv` `wifi` `ap` `qr_code`

<table>
	<thead>
		<tr>
			<th>Global Header</th>
			<th>Menu</th>
			<th>Improv</th>
		</tr>
	</thead>
	<tbody>
	<tr>
		<td><img alt="Home & Global Header" src="static/screen_server/index.bmp" width=240></td>
		<td><img alt="Graphical Display Menu" src="static/screen_server/menu-open.bmp" width=240></td>
		<td><img alt="Bluetooth / Improv / Access Point" src="static/screen_server/improv.bmp" width=240></td>
	</tr>
	</tbody>
</table>

### Watch faces

<table>
  <thead>
    <tr>
      <th>Basic</th>
      <th>Watch Hands</th>
      <th>Image as Face</th>
      <th>Color by time</th>
    </tr>
  </thead>
<tbody>
	<tr>
		<td><img alt="" src="static/screen_server/watch.bmp" width=256></td>
		<td><img alt="" src="static/screen_server/watch-face-new.bmp" width=256></td>
		<td><img alt="" src="static/screen_server/watch-face.bmp" width=256></td>
    <td><img alt="" src="static/screen_server/watch-face-dynamic.bmp" width=256></td>
	</tr>
</tbody>
</table>

### Navigation

- [x] 4 + 4 Swipe Gestures (up, down, left, right) + diagonal
- [x] `graphical_display_menu`
- [x] configured `touchscreen` `binary_sensor` grids to toggle `switch`, press `button` etc.

<table>
  <thead>
    <tr>
      <th>Menu</th>
      <th>Grid in use</th>
      <th>3x3 Grid</th>
      <th>4x4 Grid</th>
    </tr>
  </thead>
  <tbody>
  <tr>
    <td><img alt="Graphical Display Menu" src="static/screen_server/menu.bmp" width=240></td>
    <td><img alt="" src="static/screen_server/sensors.bmp"></td>
    <td><img alt="Color test" src="static/screen_server/test-color.bmp" width=256></td>
    <td><img alt="Grid test" src="static/screen_server/test-grid.bmp" width=256></td>
  </tr>
  </tbody>
</table>

***

##  Screenshot Web Server

> [!TIP]
> See and share what's on your display. 🦄
> - [x] Like an `esp32_camera web_server` but for your display. ✨
> - [x] Can be used with **any** `display` 🌈
<details>
  <summary><code>yaml</code></summary>

```yaml
screen_server:
  - port: 888
    display: lcd
```
</details>

<table>
	<thead>
		<tr>
			<th>Online image</th>
			<th>Spotify Cover Art</th>
			<th>Color Test</th>
		</tr>
	</thead>
	<tbody>
	<tr>
		<td><img alt="online_image" src="static/screen_server/image-online.bmp" width=256></td>
		<td><img alt="Spotify Albym Art" src="static/screen_server/image-spotify.bmp" width=256></td>
		<td><img alt="Color test" src="static/screen_server/test-error.bmp" width=256></td>
	</tr>
	</tbody>
</table>

<!--

<table>
	<tr>
		<td><img alt="Lilygo" src="static/logos/lilygo.svg" height="32">
		<td><img alt="Espressif" src="static/logos/espressif.svg" height="32"></td>
		<td><img alt="Esphome" src="static/logos/esphome.svg" height="32"></td>
		<td><a href="https://veli.ee"><img src="https://veli.ee/northeast/logo?t=reverse+engineered&c=f5a012&b=e7352c&t2=%20📟" height="48" alt="Eesti"></a></td>
	</tr>
</table>
-->



> [!NOTE]
> <sub>All product names, logos, and brands are property of their respective owners. All company, product and service names used are for identification purposes only. Use of these names, logos, and brands does not imply endorsement. </sub>
> 
> > *"Anyway, regardless of your opinion on people getting paid for their work, or holding open source code hostage (depending on your perspective)"* 😅
> 
> > To release the full source, I would like to achieve a sponsorship goal.
> >
> > [![uwu](https://img.shields.io/github/sponsors/velijv?logo=githubsponsors&label=sponsor%20🥺%20me&style=flat-square&labelColor=rgba(0,0,0,0)&color=rgba(234,74,170,0.5) "for jsut 1 doolar you can lead a por man to fish")](https://github.com/sponsors/velijv) [![Buy Me a Cofffee](https://img.shields.io/badge/Gift%20a%20Covfefe-red?logo=buymeacoffee&logoColor=fff&labelColor=rgba(0,0,0,0)&color=rgba(128,128,1,0.1)&style=flat-square "help me replace my blown up devices")](https://www.buymeacoffee.com/velijv) [![PayPal](https://img.shields.io/badge/Tip%20my%20jar-red?logo=paypal&logoColor=fff&style=flat-square&labelColor=rgba(0,156,222,0)&color=rgba(1,33,105,0.1) "Purchase new gadgets to hack for you")](https://paypal.me/velijohan) [![About Sponsoring](https://img.shields.io/badge/Veli_🤝-why_sponsor-red?&logoColor=fff&style=flat-square&labelColor=rgba(124,124,124,0)&color=rgba(124,124,124,0.1) "Read about me and more ways to Sponsor")](https://veli.ee/sponsor)
>
> [![LILYGO® T-Watch S3 ESPHome © 2024 by Veli-Johan Veromann is licensed under Attribution-NonCommercial-NoDerivatives 4.0 International](https://img.shields.io/badge/Licence-CC--BY--NC--ND%204.0-rgba%280%2C0%2C0%2C0%29?logo=CreativeCommons&logoColor=rgba(231,53,44,1)&labelColor=rgba(231,53,44,0)&style=flat-square&color=rgba(231,53,44,0.1))](https://creativecommons.org/licenses/by-nc/4.0/ "LILYGO® T-Watch S3 ESPHome © 2024 by Veli-Johan Veromann is licensed under Attribution-NonCommercial-NoDerivatives 4.0 International") [![LILYGO®](https://img.shields.io/badge/LILYGO-f5a012.svg?logo=data%3Aimage%2Fsvg%2Bxml%3Bbase64%2CPHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIGZpbGw9Im5vbmUiIHZpZXdCb3g9IjAgMCAyNCAyNCI+CiAgPGcgY2xpcC1wYXRoPSJ1cmwoI2EpIj4KICAgIDxwYXRoIGZpbGw9IiNGNUEwMTIiIGZpbGwtcnVsZT0iZXZlbm9kZCIgZD0ibTE3LjYuMy0uNi42YzAgLjMtLjMuNC0xIC40LTEgLjEtMS41LjUtMS44IDEuMi0uMi40LS4zLjUtLjYuNGgtMS4xYy0uNiAwLTEtLjEtMS0uMy0uNS0uNS0xLjctLjItMi41LjctLjQuNS0xLjEgMS41LTEuMSAxLjdsLjQuMmMuNC4xLjQuMS4yLjYtLjMuNC0uNC41LTEgLjUtMS4zIDAtMS40IDEtLjIgMSAuNi4xLjYuMS42LjggMCAuNi42IDIuNC45IDIuNGwuNy4zYy42LjUgMS44LjggMi4zLjcuMy0uMS4zIDAgLjMgMXMwIDEtLjQgMWMtLjYgMC0xLjYuNS0yLjIgMUw5IDE1bC0xLjQtLjRhMTEgMTEgMCAwIDAtMi0uNWwtMS44LS4zYy0xLS4yLTEuMi0uNC0xLjMtLjdsLS4yLTIuNi0uMS0yLjljMC0uNiAwLS42LjQtLjguNS0uMS41LS4yLjYtLjcgMC0uNiAwLS42LS41LS44QzIgNSAyIDQuOSAyLjMgMy44Yy4zLTEgLjQtMS45IDAtMS45LS4yIDAtLjQuNS0uNCAxLjJzLS4yLjQtLjYtLjhDLjcuNCAwIC4xIDAgMS43YzAgMSAuNCAyLjMuOSAyLjhsLjQuNS0uNi4zYy0uNS4yLS42LjItLjUuOCAwIC41LjEuNi42LjcuNi4yLjYuMy43IDQgLjEgMy4zIDAgMy4zIDIgMy44LjkuMiAxLjYuNSAxLjcuNmwxLjMuNGMxLjMuMiAyIC40IDEuOC42bC0uMiAxYy0uNCAxLjYuNCAzIDIgMy44bC45LjR2Mi4zaDMuNWwtLjItLjdjLS4zLTEuNC0uMi0xLjUuNy0yYTQgNCAwIDAgMCAyLjEtMi4ybC4yLTFzLjQuMSAxIC42bDEgLjggMS44IDEgMiAxLjNjLjQgMCAuOS0uMy45LS42IDAtLjItMS0xLjItMi4yLTIuNC0yLTItMi41LTIuNS0xLjctMi4xLjYuMy44LjIgMS4yLS41LjYtLjkgMi43LTUuNCAyLjctNS44IDAtLjEtLjItLjQtLjUtLjZsLTQuNC0yYy0uMiAwLS41LjQtLjcuOC0uNiAxLTIuNSA1LjMtMi41IDUuOHMwIC40LS42LjFsLTEuNC0uNC0uOC0uMnYtMWwtLjItMS4xYzAtLjIgMS4yLTEuMiAxLjktMS41LjctLjQgMi0zLjEgMi00LjMtLjEtLjctLjEtLjguNC0xIC4zIDAgLjYtLjIuOC0uNGEyIDIgMCAwIDAgMC0xLjdjLS4xLS4zIDAtLjQuNS0uNy44LS41IDEuMi0xLjEuNy0xLjYtLjMtLjQtMS0uNC0xLjYgMFpNMTIgNS4xdjEuM2MwIDItLjggMi44LTIgMi4zLS44LS4zLTEtLjYtMS0xLjUgMC0xLjMuNy0yLjEgMS4zLTEuNS4zLjMuMyAxLjYgMCAyLjItLjIuNCAwIC43LjQuNi41LS4yLjgtMSAuOC0ydi0xaC0xLjNsLTEtLjEtLjUuN2E0IDQgMCAwIDAtLjMgMi44Yy4yLjcuNC44IDEgLjUuMy0uMS4zLS4xIDAgLjMtLjMuNS0uMy41IDAgLjcgMS4zIDEgMyAuOSA0LjUtLjNsLjUtLjQtLjgtMS41TDEyIDV2LjFabS0xMC43LjcuMy4yYy4xIDAgLjIgMCAuMi4yIDAgLjEtLjEuMi0uMi4xbC0uMi4xLjYuMmMuNSAwIC42IDAgLjYtLjRzLS41LS43LTEtLjdjLS40IDAtLjUgMC0uMy4zWm01LjYuOWMtLjIuMiAwIC40LjYuNC40IDAgLjYtLjEuNi0uMyAwLS4xLS4yLS4yLS42LS4ySDdsLS4xLjFaTTE4LjUgOWMtLjcgMS4zLTIuMiA0LjgtMi4yIDUgMCAuMi4zLjQuOC42IDEgLjQgMSAuNC44LjEgMCAwLS4yLS4yLS4zLS4xLS4yIDAtLjIgMCAwLS40bC4yLS42LS4yLjRjLS4yLjUtLjYuNi0uOC4zIDAtLjIuMy0xLjEuNS0xLjF2LjJjLS4xLjIgMCAuMS43LS4xbC42LS4yLS40LS4xYy0uMyAwLS41LS4yLS41LS4zIDAtLjQuNy0xLjYgMS0xLjYgMCAwIC4yLS4xLjItLjMuMS0uMi4zLS4zLjQtLjIuMi4xLjIuMiAwIC42LS4zLjYtLjQuOS0uMi45bC43LTEuM2MuNC0xIC42LTEuMy44LTEuMi4yIDAgLjMgMCAuNC0uMy4xLS4yLjMtLjIuNC0uMS4yIDAgMCAuNC0uNSAxLjdhMjYgMjYgMCAwIDAtLjggMS43bC4zLjFjLjIgMCAuMiAwIC4xLjNsLS4yLjZjMCAuMy0uMS4zLS42IDBsLS42LS4yLjQuOGMuMSAwIC4yLjEuMS4yIDAgLjUgMCAuNi4zLjMuMS0uMy4yLS40LjMtLjJ2LjVjLS4yLjEtLjIuMy0uMi40bC4yLS4zYy4zLS41LjYtLjYuNi0uM2wtLjMuN2MtLjIuNC0uMy40LS41LjMgMC0uMi0uMi0uMi0uMiAwbC42LjMuMy0uNmMuMS0uMy4zLS41LjQtLjVsLS4yLjYtLjIuN2MuMiAwIDMtNi4xIDMtNi4zbC00LTEuOC0uNy0uMy0uNSAxVjlabTEuNyAxLjN2LjJjLjIgMCAuMy0uMS4zLS4ybC0uMS0uMi0uMi4yWk0yMCAxM2MwIC4xIDAgLjIuMS4xbC4yLS4yaC0uMmMtLjIgMC0uMSAwLS4xLjFabS0zLjQuN2MtLjIuMy0uMi41IDAgLjRsLjItLjctLjIuM1ptLS4xIDEuNC42IDFjLjIuNS40LjggMS4zIDEuM2wyLjMgMS40Yy4yLS4yLTEuNC0xLjgtMS45LTJhLjkuOSAwIDAgMS0uNS0uN2MtLjEtLjQtLjMtLjYtMS0xbC0xLjEtLjVzMCAuMy4zLjVaIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiLz4KICA8L2c+CiAgPGRlZnM+CiAgICA8Y2xpcFBhdGggaWQ9ImEiPgogICAgICA8cGF0aCBmaWxsPSIjZmZmIiBkPSJNMCAwaDI0djI0SDB6Ii8+CiAgICA8L2NsaXBQYXRoPgogIDwvZGVmcz4KPC9zdmc+Cg==&logoColor=fff&labelColor=rgba(0,0,0,0)&color=rgba(245,160,18,0.1)&style=flat-square
)](https://github.com/search?q=lilygo) [![Espressif](https://img.shields.io/badge/ESP32S3%20N16R8V-e7352c.svg?logo=Espressif&logoColor=e7352c&labelColor=rgba(0,0,0,0)&color=rgba(231,53,44,0.1)&style=flat-square
)](https://github.com/espressif/) [![ESPHome](https://img.shields.io/badge/ESPHome-000?logo=Esphome&logoColor=808080&labelColor=rgba(0,0,0,0)&color=rgba(33,33,33,0.1)&style=flat-square)](https://github.com/esphome/esphome) [![Home Assistant](https://img.shields.io/badge/Home%20Assistant-03A9F4?logo=HomeAssistant&logoColor=1abcf2&labelColor=rgba(0,0,0,0)&color=rgba(26,188,242,0.1)&style=flat-square)](https://my.home-assistant.io/redirect/config_flow_start/?domain=esphome)

![GitHub repo file or directory count](https://img.shields.io/github/directory-file-count/velijv/LILYGO-T-Watch-S3-ESPHome) ![GitHub repo size](https://img.shields.io/github/repo-size/velijv/LILYGO-T-Watch-S3-ESPHome?style=flat-square) ![GitHub commit activity](https://img.shields.io/github/commit-activity/y/velijv/LILYGO-T-Watch-S3-ESPHome)




<!--
> [!NOTE]
> Useful information that users should know, even when skimming content.

> [!TIP]
> Helpful advice for doing things better or more easily.

> [!IMPORTANT]
> Key information users need to know to achieve their goal.

> [!WARNING]
> Urgent info that needs immediate user attention to avoid problems.

> [!CAUTION]
> Advises about risks or negative outcomes of certain actions.
-->

