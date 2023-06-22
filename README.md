# Washing-Machine-Sonoff-POW-Origin-Esphome

This is a Fork for [Gio-dot](https://github.com/Gio-dot) work.

I use a Sonoff POW Origin to monitor my washing machine activity in Home assistant; traditional approach to do so is to decode washing phases using Home assistant sensors/templates. Thanks to ESPHome firmware this can be easily made directly in the Sonoff Pow R2 cleaning up Home assistant configuration.
Five binary sensors (RUN, WASHING, CENTRIFUGE, DRAIN, END) are automatically exposed by the Sonoff Pow to Home assistant frontend.

RUN or END sensors can be easily used in Home assistant automations to send messages to Telegram or Google home etc. to  warn that the cycle has ended. See Home assistant example: [home_assistant_w_machine.yaml](https://github.com/Gio-dot/Washing-Machine-Sonoff-Pow-R2-Esphome/blob/master/home_assistant_w_machine.yaml)

For instructions about ESPHome installation see: https://esphome.io/index.html

### New Esphome and Home assistant code 23/06/2023
Changelog:
1. Added a text sensor to show the elapsed time for the current run.
2. Added a text sensor to store the last run details "Finish Time/Date and Elapsed Time". This is populated after each run end.
3. Added most timing parameters into the substitutions part to easly customize without going through the whole code.
4. Added some logging

Use this yaml code to create your ESPHome firmware [Sonoff_POW_Origin_WashingMachine_Plus.yaml](https://github.com/wbsoul/Washing-Machine-Sonoff-Pow-Origin-Esphome/edit/master/Sonoff_POW_Origin_WashingMachine_Plus.yaml)

## How it works

<img src="https://github.com/wbsoul/Washing-Machine-Sonoff-Pow-Origin-Esphome/raw/master/img/Sonoff_POW_Origin_WashingMachine_Plus.png" width="300">
This image show Home assitant card from Sonoff Pow Origin. Washing phases are shown in sequence from bottom to top. At the end of the cycle all phases (except RUN) remains lighted. At next cycle start they are resetted.
Sonoff Pow blue Led is lighted when a cycle is running and turned off at the cycle end.

