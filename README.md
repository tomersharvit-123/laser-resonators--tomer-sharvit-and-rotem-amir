# Laser Resonator, Passive Q Switching and TEM in a Diode Pumped Nd:YAG Lase


Diode-pumped Nd:YAG lasers provide continuous and pulsed light for applications such as ma-
terial processing and distance measurement. We first calibrated the 808 nm pump diode, finding
a linear relation between power and current with a slope of (0.905 ± 0.035) W A−1. Using this
calibration, we obtained a continuous-wave slope efficiency of (8.44 ± 0.49)% at 1064 nm and an ex-
trapolated pump threshold of (348 ± 50) mW. Varying the diode temperature at a current of 1.50 A
gave the highest output near 31 ◦C. To examine the beam’s spatial structure, we analyzed four
supplied images and found that a Hermite–Gaussian model described three intensity profiles well
but fitted the fourth poorly. Introducing a Cr4+:YAG saturable absorber produced pulses whose
repetition frequency increased from 3.2 to 6.9 kHz as the pump current increased. Their durations
ranged from 13.0 to 15.2 ns at full width at half maximum, with deviations from a linear dependence
on pump power.


lets start with out mesurment:
### `מדידה1- לייזרים.xlsx`
**Description:** Pump diode power calibration data (Sec. 2.1) measuring raw and calibrated pump power (with/without ND filter) vs. diode current at constant temperature ($10.9^\circ\text{C}$).
**Columns:** Diode current (`I(A)`), raw power (`P(mW`), calibrated pump powers (`P_noND(mW)`, `P_withND(mW)`), and measurement uncertainties.

### `ניסוי לייזרים- מדידה 2 (טמפ קבוע זרם לא).xlsx`
**Description:** CW lasing characterization data (Sec. 3.1) measuring Nd:YAG output power vs. diode current and calibrated pump power to determine the lasing threshold and slope efficiency.
**Columns:** Diode current (`I(A)`), calibrated pump power (`P_in(mW)`), raw and calibrated laser output power (`P_out(mw)`), and uncertainties.

### `לייזרים -מדידות 3, זרם קבוע טמפ לא.xlsx`
**Description:** Pump temperature optimization data (Sec. 3.2) scanning diode temperature upward from $20^\circ\text{C}$ at constant currents ($1.5\text{ A}$ and $1.75\text{ A}$) to find the optimal working point.
**Columns:** Constant diode currents (`I(A)`), diode temperature (`T©`), raw and calibrated output power (`P(mw)`, `P(mW)`), and uncertainties.

### `Qswiching-חלק1.xlsx`
**Description:** Passive Q-switching pulse duration data (Sec. 5) measuring pulse width (FWHM) as a function of diode current and calibrated pump power using a Cr:YAG crystal.
**Columns:** Diode current (`I(A)`), calibrated pump power (`P_in(mW)`), pulse width (`FWHM(ns)`), and corresponding uncertainties.

### `Qswiching-חלק2.xlsx`
**Description:** Passive Q-switching repetition rate data (Sec. 5 & Appendix C) measuring pulse repetition frequency vs. pump power and calculated pump rate $B$ for theoretical fitting.
**Columns:** Repetition frequency (`FERQ(KH)`), diode current (`I(A)`), calibrated pump power (`P_pump(mW)`), volumetric pump rate (`B(M^-3 s^-1)`), and uncertainties.

* **`peak-i=1.69.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 1.69\text{ A}$ with a measured FWHM of $13.4\text{ ns}$.
* **`peak-i=1.74.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 1.74\text{ A}$ with a measured FWHM of $13.4\text{ ns}$.
* **`peak-i=1.79.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 1.79\text{ A}$ with a measured FWHM of $13.7\text{ ns}$.
* **`peak-i=1.84.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 1.84\text{ A}$ with a measured FWHM of $13.4\text{ ns}$.
* **`peak-i=1.89.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 1.89\text{ A}$ with a measured FWHM of $13.0\text{ ns}$.
* **`peak-i=1.94.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 1.94\text{ A}$ with a measured FWHM of $13.3\text{ ns}$.
* **`peak-i=1.99.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 1.99\text{ A}$ with a measured FWHM of $15.2\text{ ns}$.
* **`peak-i=2.04.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 2.04\text{ A}$ with a measured FWHM of $14.4\text{ ns}$.
* **`peak-i=2.07.png`**: Oscilloscope capture of a passive Q-switched laser pulse at $I = 2.07\text{ A}$ with a measured FWHM of $15.0\text{ ns}$.
```[cite: 21, 22, 23, 24, 25, 26, 27, 28, 29]


### lasers-part1 (2).ipynb is our first colab phyton which does a linear fit of the diode output Power in the Y axis and the current I in the X axis.
* **Statistical Evaluation:** Computes residuals, reduced chi-squared ($\chi^2_\nu$), and the corresponding $p$-value to assess goodness of fit.
* **Visualization:** Generates formatted plots comparing the experimental data against the fitted model.


### lasers-part2 (1).ipynb this is a colab phyton script which does a linear fit of the diode output Power of the Nd:YAG in the Y axis and the diode Pumping power in the X axis.
* **Statistical Evaluation:** Computes residuals, reduced chi-squared ($\chi^2_\nu$), and the corresponding $p$-value to assess goodness of fit.
* **Visualization:** Generates formatted plots comparing the experimental data against the fitted model.


### lasers-part3 (2).ipynb is a colab phyton which display on a graph the diode output Power in the Y axis and the tempature of the diode in the X axis.
* **Visualization:** Generates  the experimental dataon a graph.


### TEM00 (2).ipynb is Colab notebook that loads a laser mode image, converts it to grayscale, crops and sums it into a 1D profile, and fits a Hermite-Gauss model to calculate beam center, width, and mode contributions.Inputs: A laser mode image file (e.g., TEM00new.jpg), defaulting to a generated synthetic image if the file is missing.Outputs: Printed fit parameters (beam center, width, $R^2$, and mode coefficients $A_0$–$A_3$) and two plots displaying the cropped mode image and the normalized 1D intensity profile.

### TEM01 (2).ipynb is Colab notebook that loads a laser mode image, converts it to grayscale, crops and sums it into a 1D profile, and fits a Hermite-Gauss model to calculate beam center, width, and mode contributions.Inputs: A laser mode image file (e.g., TEM01.jpg), defaulting to a generated synthetic image if the file is missing.Outputs: Printed fit parameters (beam center, width, $R^2$, and mode coefficients $A_0$–$A_3$) and two plots displaying the cropped mode image and the normalized 1D intensity profile.

### TEM02 (2).ipynb is Colab notebook that loads a laser mode image, converts it to grayscale, crops and sums it into a 1D profile, and fits a Hermite-Gauss model to calculate beam center, width, and mode contributions.Inputs: A laser mode image file (e.g., TEM02.jpg), defaulting to a generated synthetic image if the file is missing.Outputs: Printed fit parameters (beam center, width, $R^2$, and mode coefficients $A_0$–$A_3$) and two plots displaying the cropped mode image and the normalized 1D intensity profile.

### TEM03 (3).ipynb is Colab notebook that loads a laser mode image, converts it to grayscale, crops and sums it into a 1D profile, and fits a Hermite-Gauss model to calculate beam center, width, and mode contributions.Inputs: A laser mode image file (e.g., TEM03.jpg), defaulting to a generated synthetic image if the file is missing.Outputs: Printed fit parameters (beam center, width, $R^2$, and mode coefficients $A_0$–$A_3$) and two plots displaying the cropped mode image and the normalized 1D intensity profile.

### lasers-part5 (1).ipynb this is a colab phyton script
* **Model Fitting:** Uses linear interpolation  to fit the `qswitch_freq` physics model to the experimental dataset.
* **Statistical Evaluation:** Computes residuals, reduced chi-squared ($\chi^2_\nu$), and the corresponding $p$-value to assess goodness of fit.
* **Visualization:** Generates formatted plots comparing the experimental data against the fitted model.

### lasers-part6 (5).ipynb this is a colab phyton script
* **Model Fitting:** Uses linear interpolation to fit the FWHM in the Y axis and B in the x axis.
* **Statistical Evaluation:** Computes residuals, reduced chi-squared ($\chi^2_\nu$), and the corresponding $p$-value to assess goodness of fit.
* **Visualization:** Generates formatted plots comparing the experimental data against the fitted model.



