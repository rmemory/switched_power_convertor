A switched and linear regulated, are both common DC power supplies, which convert AC to DC. Switched supplies have the advantage of being much more efficient (80% vs 40%). The disadvantage of Switched supplies is they typically also produce residual ac noise and electromagnetic interference due to conversion of the incoming AC voltage to a higher frequency which allows using a smaller, more efficient transformer. On the other hand, linear regulated are larger, and disappate more heat. 

This circuit will use a switched power convertor, to allow switching from one DC voltage to another.

Lets say we need to power: Motors, microcontroller, sensors, audio etc, all of which have their own unique DC voltage requirements. A single cell battery may produce 3.7V (3.0 - 4.2V), while needing to be charged at 4.2V. Each of these are their own power domains. Some domains may need to boosted.

This circuit will provide two power domains: One for motors and servos at 6V, and another for digital and sensors at 3.3V. 

Boosts convertors go from a lower voltage to a higher voltage. Buck convertors go from a higher voltage to a lower convertor. Thus, this project will be a Buck-Boost convertor, to handle both.

For a buck convertor, an inductor is used internally to "store magnetic energy" as the convertor switches back back and forth from different voltages. For example, when operating in buck mode, the input voltage comes in as a PWM wave, and the inductor is used to create a flat, lower DC voltage. A diode provides the rectifier (only allowing positive part of the AC), an inductor, a capacitor, and the load in a parallel with the capacitor. As the capacitor reaches the desired voltage, the switch opens, while the inductor keeps current flowing until the capacitor voltage drops below the threshold output voltage, and the switch is opened again. Essentially, the usage of the inductor and switch (PWM effect), allows the regulator to produce a lower voltage than the input.

For a boost convertor, is relatively new. It allows usage of a single cell, instead of multiple battery cells. The power source goes into the inductor. The capacitor is in parallel with the output load. The current flows through the inductor to build up energy, the switch is opened, flowing into the capacitor and load. The extra energy from the inductor, produces a voltage spike (higher voltage). As the voltage drops at the output, the switch is closed, allowing the inductor to build up energy again.

https://en.wikipedia.org/wiki/Buck_converter
https://en.wikipedia.org/wiki/Boost_converter
