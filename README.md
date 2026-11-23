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


# Laser Resonator, Passive Q Switching and TEM in a Diode Pumped Nd:YAG Laser

## Overview
This repository contains the experimental datasets, oscilloscope pulse captures, and Python (Google Colab) analysis notebooks used to characterize a diode-pumped Nd:YAG laser resonator. The scripts perform orthogonal distance regression (ODR) fits for pump-diode calibration, continuous-wave (CW) lasing efficiency, temperature optimization, Hermite–Gaussian transverse electromagnetic (TEM) mode decomposition, and passively Q-switched pulse dynamics using a Cr⁴⁺:YAG saturable absorber. Running these notebooks reproduces all statistical metrics, fit parameters, and publication figures presented in the accompanying paper.

---

## Data Files (Excel)

### `מדידה1- לייזרים.xlsx`
- **Description:** 808 nm pump-diode power calibration data (at constant $T = 10.9^\circ\text{C}$), comparing raw and calibrated pump powers with and without the ND2 filter factor.
- **Columns:** Diode current (`I(A)`), raw power (`P(mW)`), calibrated pump powers (`P_noND(mW)`, `P_withND(mW)`), and measurement uncertainties.

### `ניסוי לייזרים- מדידה 2 (טמפ קבוע זרם לא).xlsx`
- **Description:** CW 1064 nm lasing characterization data measuring Nd:YAG output power vs. diode current and calibrated pump power to extract threshold and slope efficiency.
- **Columns:** Diode current (`I(A)`), calibrated pump power (`P_in(mW)`), raw and calibrated laser output power (`P_out(mw)`), and uncertainties.

### `לייזרים -מדידות 3, זרם קבוע טמפ לא.xlsx`
- **Description:** Pump-diode temperature optimization data scanning upward from $20^\circ\text{C}$ at fixed currents ($1.50\text{ A}$ and $1.75\text{ A}$) to identify the optimal working point ($31^\circ\text{C}$).
- **Columns:** Diode current (`I(A)`), diode temperature (`T(C)`), raw and calibrated output power (`P(mw)`, `P(mW)`), and uncertainties.

### `Qswiching-חלק1.xlsx`
- **Description:** Passive Q-switching pulse-duration dataset measuring pulse width (FWHM) vs. diode current and calibrated pump power with a Cr⁴⁺:YAG absorber.
- **Columns:** Diode current (`I(A)`), calibrated pump power (`P_in(mW)`), pulse width (`FWHM(ns)`), and uncertainties.

### `Qswiching-חלק2.xlsx`
- **Description:** Passive Q-switching repetition-rate dataset measuring pulse repetition frequency vs. pump power and volumetric pump rate $B$ for nonlinear theoretical fitting.
- **Columns:** Repetition frequency (`FERQ(KH)`), diode current (`I(A)`), calibrated pump power (`P_pump(mW)`), volumetric pump rate (`B(M^-3 s^-1)`), and uncertainties.

---

## Oscilloscope Pulse Captures
Raw oscilloscope screenshots used to extract passive Q-switching pulse durations (FWHM) across pump currents:
- **`peak-i=1.69.png`** ($I = 1.69\text{ A}$, $\text{FWHM} = 13.4\text{ ns}$) | **`peak-i=1.74.png`** ($I = 1.74\text{ A}$, $\text{FWHM} = 13.4\text{ ns}$) | **`peak-i=1.79.png`** ($I = 1.79\text{ A}$, $\text{FWHM} = 13.7\text{ ns}$)
- **`peak-i=1.84.png`** ($I = 1.84\text{ A}$, $\text{FWHM} = 13.4\text{ ns}$) | **`peak-i=1.89.png`** ($I = 1.89\text{ A}$, $\text{FWHM} = 13.0\text{ ns}$) | **`peak-i=1.94.png`** ($I = 1.94\text{ A}$, $\text{FWHM} = 13.3\text{ ns}$)
- **`peak-i=1.99.png`** ($I = 1.99\text{ A}$, $\text{FWHM} = 15.2\text{ ns}$) | **`peak-i=2.04.png`** ($I = 2.04\text{ A}$, $\text{FWHM} = 14.4\text{ ns}$) | **`peak-i=2.07.png`** ($I = 2.07\text{ A}$, $\text{FWHM} = 15.0\text{ ns}$)

---

## Analysis Notebooks (Google Colab / Python)

### `lasers-part1 (2).ipynb`
- **Description:** Performs a linear ODR fit of calibrated 808 nm pump-diode power vs. diode current, evaluating residuals, $\chi^2_{\mathrm{red}}$, and $p$-value.
- **Inputs:** `מדידה1- לייזרים.xlsx`.
- **Outputs:** Printed slope/threshold parameters and formatted calibration fit and residual plots (including ND2 filter comparison for Appendix A).

### `lasers-part2 (1).ipynb`
- **Description:** Performs a linear ODR fit of CW 1064 nm Nd:YAG output power vs. calibrated pump power to determine slope efficiency and lasing threshold.
- **Inputs:** `ניסוי לייזרים- מדידה 2 (טמפ קבוע זרם לא).xlsx`.
- **Outputs:** Printed fit statistics ($\chi^2_{\mathrm{red}}$, $p$-value, $R^2$) and formatted CW power-conversion fit and residual plots.

### `lasers-part3 (2).ipynb`
- **Description:** Plots calibrated 1064 nm laser output power as a function of pump-diode temperature with error bars to locate the optimal working temperature.
- **Inputs:** `לייזרים -מדידות 3, זרם קבוע טמפ לא.xlsx`.
- **Outputs:** Formatted temperature-scan figure used to select $T_{\mathrm{work}} = 31^\circ\text{C}$.

### `TEM00 (2).ipynb`
- **Description:** Converts the fundamental-mode image to grayscale, crops and sums vertically to a 1D profile, and fits a 4-term Hermite–Gaussian intensity model.
- **Inputs:** `TEM00new.jpg` (falls back to a synthetic Gaussian image if missing).
- **Outputs:** Fitted parameters ($x_0$, $w$, $R^2$, $A_0$–$A_3$) and plots of the cropped beam image and normalized 1D profile.

### `TEM01 (2).ipynb`
- **Description:** Processes the nominal $\mathrm{TEM}_{1,0}$ image via grayscale conversion, cropping, vertical summation, and nonlinear least-squares Hermite–Gaussian fitting.
- **Inputs:** `TEM10.jpg` (falls back to a synthetic image if missing).
- **Outputs:** Fitted parameters ($x_0$, $w$, $R^2$, $A_0$–$A_3$) and plots of the cropped beam image and normalized 1D profile.

### `TEM02 (2).ipynb`
- **Description:** Rotates the nominal $\mathrm{TEM}_{2,0}$ image ($31.5^\circ$) to align nodal axes, crops and sums vertically, and fits the 4-term Hermite–Gaussian model.
- **Inputs:** `TEM20.jpg` (falls back to a synthetic image if missing).
- **Outputs:** Fitted parameters ($x_0$, $w$, $R^2$, $A_0$–$A_3$) and plots of the rotated/cropped beam image and normalized 1D profile.

### `TEM03 (3).ipynb`
- **Description:** Processes the replacement nominal $\mathrm{TEM}_{0,3}$ image via grayscale conversion, cropping, vertical summation, and Hermite–Gaussian fitting.
- **Inputs:** `TEM03.jpg` (falls back to a synthetic image if missing).
- **Outputs:** Fitted parameters ($x_0$, $w$, $R^2$, $A_0$–$A_3$) and plots of the cropped beam image and normalized 1D profile.

### `lasers-part5 (1).ipynb`
- **Description:** Performs a nonlinear ODR fit of passive Q-switching repetition frequency vs. volumetric pump rate $B$ using the Zhang et al. model (fixed $\tau_a = 230\,\mu\text{s}$, $\beta = 0.4$).
- **Inputs:** `Qswiching-חלק2.xlsx`.
- **Outputs:** Fitted threshold pump rate $B_{\mathrm{th}}$, $\chi^2_{\mathrm{red}}$, $p$-value, and separate formatted fit and residual plots.

### `lasers-part6 (5).ipynb`
- **Description:** Performs a linear ODR fit of passive Q-switching pulse duration (FWHM) vs. calibrated pump power $P_{\mathrm{pump}}$ and evaluates goodness of fit.
- **Inputs:** `Qswiching-חלק1.xlsx`.
- **Outputs:** Printed slope/intercept, $\chi^2_{\mathrm{red}}$, $p$-value, and formatted FWHM fit and residual plots.
