---
comments: true
layout: post
section-type: post
tags: [science]
title: First test chamber constructed
---

## Narrative
We have acquired some sensors, and constructed the first of many test chambers. This chamber contains the evaporator coils of the heat pump and sensors. This data is available on [GitHub](https://github.com/openawg/openawg).

## Problem 0

We need to evaluate different sensors for use in our prototypes and experiments. A freezer will help us understand how the sensor performs in environments below 0ºC.

## Hypothesis 0
[Adafruit’s AM2302 (wired DHT22) temperature-humidity sensor](http://www.adafruit.com/products/393) will be appropriate for the temperature and humidity measurements we need to perform.

## Procedure & Materials 0
We used a [BeagleBone Black](https://beagleboard.org/black), [Adafruit’s AM2302](https://www.adafruit.com/product/393), and an Anker USB battery pack to measure the environment inside of a freezer.

[![BeagleBone Black chillin' in freezer](/assets/bbbfreezer.jpg)](/assets/bbbfreezer.jpg){:target="\_blank"}
<a name="fig0">&nbsp;</a>\[fig0\]: [BeagleBone Black chillin' in freezer](/assets/bbbfreezer.jpg){:target="\_blank"}

[![Freezer test data](/assets/freezer1.png)](/assets/freezer1.png){:target="\_blank"}
<a name="fig1">&nbsp;</a>\[fig1\]: [Freezer test data](/assets/freezer1.png){:target="\_blank"}

## Conclusions 0
The temperature readings from the sensor seem to be within expected ranges for a freezer. The variations in temperature might be caused by defrost cycles, or the thresholds for compressor operation. It is interesting to see how small changes in temperature greatly affect the relative humidity at this low temperature and absolute humidity.

## Problem 1
We need to gather information on heat pump performance, which will help us understand how our prototypes perform in different humidities and temperatures in order to predict and verify their performance in low-humidity conditions.

## Hypothesis 1
When insulated, the heat pump is able to pull the temperature down below 0ºC.

## Procedure & Materials 1
We used [R-5 insulation sheathing panels](http://www.homedepot.com/p/Project-Panels-FOAMULAR-1-in-x-2-ft-x-2-ft-R-5-Insulation-Sheathing-Project-Panel-PP1/203553730), [Gorilla Glue](https://en.wikipedia.org/wiki/Gorilla_Glue), and foil tape to construct an insulated box around the evaporator coils of the [modified dehumidifier](http://amzn.com/B00CEZA018).

[![Dehumidifer is all bent out of shape](/assets/modifieddehumidifier.jpg)](/assets/modifieddehumidifier.jpg){:target="\_blank"}
<a name="fig2">&nbsp;</a>\[fig2\]: [Dehumidifier is all bent out of shape](/assets/testchamber0.jpg){:target="\_blank"}

[![Test chamber 0](/assets/testchamber0.jpg)](/assets/testchamber0.jpg){:target="\_blank"}
<a name="fig3">&nbsp;</a>\[fig3\]: [Test chamber 0](/assets/testchamber0.jpg){:target="\_blank"}


We then used a [Raspberry Pi 2](https://www.raspberrypi.org/products/raspberry-pi-2-model-b/) and [Adafruit’s AM2302](https://www.adafruit.com/product/393) to measure the temperature and humidity inside the insulated chamber.

The data collection was started while the sensor was exposed to ambient conditions outside of the test chamber. The sensor was then placed into the test chamber, and the lid was closed and held in place by a giant can of Four Loko and a Mudkip plushie filled with lead pellets. Just kidding, it was actually a 1L bottle of 99.953% anhydrous isopropyl alcohol, which is functionally equivalent in several ways. The heat pump was started and operated with the lid closed for around 30 minutes. After which, we opened the lid to see what the evaporator coil looked like.

The resulting data was mangled with the equations from [here](http://andrew.rsmas.miami.edu/bmcnoldy/Humidity.html) and [this NASA technical note](http://www.nasa.gov/centers/dryden/pdf/87878main_H-937.pdf) to derive the dew point and absolute humidity. The duration of the measurement was around 1 hour.

[![Test chamber 0 data](/assets/testchamber0data.png)](/assets/testchamber0.png){:target="\_blank"}
<a name="fig4">&nbsp;</a>\[fig4\]: [Test chamber 0 data](/assets/testchamber0.png){:target="\_blank"}

The plot above shows the sensor-reported relative humidity (RH), calculated dewpoint in celsius (DWPC), sensor-reported temperature (TMPC), and calculated absolute humidity (AH) over a period of around 1 hour.

The plateau at the beginning indicates the ambient conditions outside of the test chamber, and the initial decrease in (TMPC, RH, DWPC, AH) corresponds to the initial operation of the heat pump.

The sudden increase in (TMPC, RH, DWPC, AH) corresponds to the opening of the test chamber lid for our inspection of the evaporator coils with our eyeballs.

The last decrease in (TMPC, RH, DWPC, AH) corresponds to the closure of the lid until the end of the test.

We opened the box, and within seconds, ice started forming on the top most section of the evaporator coils from the introduction of ambient air.

[![A little bit of ice](/assets/evap0.jpg)](/assets/evap0.jpg){:target="\_blank"}
<a name="fig5">&nbsp;</a>\[fig5\]: [A little bit of ice](/assets/evap0.jpg){:target="\_blank"}

[![A little bit more ice](/assets/evap1.jpg)](/assets/evap1.jpg){:target="\_blank"}
<a name="fig6">&nbsp;</a>\[fig6\]: [A little bit more ice](/assets/evap1.jpg){:target="\_blank"}

## Conclusions 1
It was interesting to see the relative humidity climb after decreasing alongside the temperature and absolute humidity. This makes sense, as the saturation vapor pressure of water vapor in air decreases with a decrease in temperature.

The test chamber seemed to have enough thermal resistance to maintain the temperature difference.

The heat pump was able to attain a temperature of -27.3ºC with an ambient of 19ºC, for a delta of 46.3ºC.

## Next steps
Test more sensors to compare the results between individual units.

Test different heat pumps to compare results between models.

Find a freezer without a defrost cycle to compare readings, and see if sensor readings stabilize.

Put the paraphernalia into a [Jupyter](http://jupyter.org/) notebook.

Find a better graphing situation.

Test 2x [AM2302 (wired DHT22)  temperature-humidity sensor](http://www.adafruit.com/products/393).

Test 2x [AM2315 - Encased I2C Temperature/Humidity Sensor](http://www.adafruit.com/products/1293).

[![Moar sensars](/assets/adafruitsensors.jpg)](/assets/adafruitsensors.jpg){:target="\_blank"}
<a name="fig6">&nbsp;</a>\[fig6\]: [Moar sensors](/assets/adafruitsensors.jpg){:target="\_blank"}
