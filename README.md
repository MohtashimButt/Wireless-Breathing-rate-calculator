# Wireless-Breathing-rate-calculator
Developed a framework to track a subject’s breathing rate using data acquired from passive RFID tags pasted on the subject’s chest
## Background
Breathing rate monitoring helps assess general personal health and gives clues to predict chronic diseases like chronic obstructive pulmonary diseases, cardiac arrest, etc. Consequently, there is a compelling need for a non-intrusive and cost-effective breathing rate monitoring system.

Although wireless sensing technologies have been developed in the research literature to monitor breathing using radio waves without physical contact, these technologies require customized radios, which are not readily available or are prone to interference. With multiple users in presence, the detection accuracy of existing systems decreases dramatically.

## How do radio signals work
For a Radio Frequency wave at frequency $f$ (Hz), the relation between frequency and wavelength is given by $$c = f \times \lambda$$ where $c$ is the speed of the EM wave in the communication medium, which, in air, is equal to the speed of light $3.0 \times 10^{8} ms^{−1}$. The reader's operation frequency is $866 MHz$, corresponding to a wavelength of $35cm$. Also, the accumulated phase θ of a sinusoidal wave of wavelength $λ$ in relation to the total distance traveled is related by $$θ = (\frac{2π}{λ} \times distance) \textnormal{mod} 2π$$, where the notation mod $2π$ represents modulo or the remainder obtained by dividing the term inside the bracket by $2π$. Since the phase is a periodic function with period $2π$ radians, the phase values will  repeat at distances separated by integer multiples of the wavelength.

## Dataset
We have two kinds of datasets:
***
* Dataset for a static person (`Staticbreathing.csv`)
* [Dataset for a person who's non-static i.e., contantly moving (`NonStaticbreathing.csv`)

## Phase Jupms
Imagine that the person is static, corresponding to which one measures a phase of let’s say $90$ degrees. As the person starts moving closer to the reader, the distance that the wave has to travel decreases and as a result the measured phase of the wave starts decreasing as well. What happens to the phase (read angle) as it continues to decrease and reaches $0$ degrees? Any further decrease wraps the angle back to $360$ degrees causing a sudden jump of $+360$ degrees ($+2π$ radians) and then starts decreasing again from a starting point of 360 degrees. 

Similarly, if the person starts moving away from the reader, the angle starts increasing and any increase beyond $360$ degree wraps it back to $0$ degrees and then starts increasing from $0$ degrees. This will manifest itself as a sudden jump of $-360$ degrees ($-2π$ radians) in the sense that the angle changes from $360$ degrees back to $0$ degrees. In summary, due to the wrap-around effect of phase/angles, the phase measurement signal may have these abrupt changes of $± 360$ degrees (or $± 2𝜋$ radians) that must be removed for our signal processing algorithms to make sense of the trends. 
![staticRaw](https://github.com/MohtashimButt/Wireless-Breathing-rate-calculator/assets/87702903/857ff9a4-6282-4523-a1e0-1df272e33e8b)
