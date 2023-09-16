# Wireless-Breathing-rate-calculator
Developed a framework to track a subject’s breathing rate using data acquired from passive RFID tags pasted on the subject’s chest
## Background
Breathing rate monitoring helps assess general personal health and gives clues to predict chronic diseases like chronic obstructive pulmonary diseases, cardiac arrest, etc. Consequently, there is a compelling need for a non-intrusive and cost-effective breathing rate monitoring system.

Although wireless sensing technologies have been developed in the research literature to monitor breathing using radio waves without physical contact, these technologies require customized radios, which are not readily available or are prone to interference. With multiple users in presence, the detection accuracy of existing systems decreases dramatically.

## How radio signals work
For a Radio Frequency wave at frequency $f$ (Hz), the relation between frequency and wavelength is given by$\\$
$c = f \times λ \\$
where $c$ is the speed of the EM wave in the communication medium, which, in air, is equal to the speed of light $3.0 \times 108 ms^{−1}$. The reader's operation frequency is $866 MHz$, corresponding to a wavelength of $35cm$. Also, the accumulated phase θ of a sinusoidal wave of wavelength $λ$ in relation to the total distance traveled is related by $\\$
$θ = (\frac{2π}{λ} \times distance) \textnormal{mod} 2π\\$,
where the notation mod $2π$ represents modulo or the remainder obtained by dividing the term inside the bracket by $2π$. Since the phase is a periodic function with period $2π$ radians, the phase values will  repeat at distances separated by integer multiples of the wavelength.
