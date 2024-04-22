# Decoupled Dual-Loop RF Magnetic Field Probe

## MRI and RF Coils
Magnetic resonance imaging (MRI) requires radio frequency (RF) “coils” to excite and receive the MR signal from 1H nuclei (protons). Coils are similar to antennas: they must produce a desired field pattern and operate at a given frequency, which for MR is known as the Larmor frequency and is given by the product of the scanner’s static magnetic field (B<sub>0</sub> in tesla – T) and gyromagnetic ratio (γ = 42.58 MHz/T for protons) of the nuclei.

## Measurement of Resonant Frequency and Q
To achieve optimal performance, coils must usually be tuned to the Larmor frequency, e.g., by adjusting one or more capacitors or physical dimensions. Resonant frequency can be measured readily using a vector network analyzer (VNA) and a [single loop probe]() with an S<sub>11</sub> measurement (analogous to the dip meter measurement used in the past when VNAs were not cheap and portable). 
The coil’s sensitivity or SNR of the received signal is related to the ratio of loaded and unloaded quality factors (Q) [1]. With some corrections [2], Q can be measured using the same S<sub>11</sub> measurement above, but it is challenging because the correction depends on the strength of the coupling which is difficult to control, especially if the probe is positioned manually. It is much more convenient to use two probes and an S<sub>21</sub> measurement, in which case the Q is simply f<sub>0</sub>/∆f, where f<sub>0</sub> is the center frequency and ∆f is the FWHM of the resonance curve as shown below.

For this 2-probe measurement it is important that, in absence of the coil being tested, the coupling (or crosstalk) between the two pickup loops be as small as possible (i.e., coupling through the coil should dominate). One way to achieve this is to position the pickup loops at opposite ends of a surface coil as shown below (left). However, this strategy will not work for all coil geometries, e.g., if the coil is small, or to measure the resonance of small accessory circuits like detuning traps.

Following the work of Darrasse and Kassab [3], it has become common to overlap the two pickup loops so that their mutual inductance is zero (right). Arranging the loops orthogonally is also a means of min-imizing coupling [4]. It is common to make the pickup loops by hand using semi-rigid, hand-formable or flexible coaxial cable (https://www.uniteng.com/neildocs/references/Probing_the_Magnetic_Field_Probe.htm), but attaching them firmly together in the optimal position is often awkward and unreliable. Recently a correction strategy was developed to compensate for any remaining coupling, but for the correction to work the coupling must remain constant in time.

## Design
The motivation for this work was to make a double-loop probe that is rugged, reliable and provides consistent and sufficiently low intrinsic coupling. The design follows the principles of the single [printed shielded loop probe](), and uses a 4-layer PCB stackup in which the top and bottom layers are ground planes, while the two inner layers contain two stripline loops with appropriate overlap to minimize coupling.

Connections from the board to coaxial cables are made at the end opposite the loops through two side-launch connectors such SMA. The PCB design is provided in both [KiCAD]() and Gerber format.

## References
[1]	W. A. Edelstein, G. H. Glover, C. J. Hardy, and R. W. Redington, “The Intrinsic Signal-to-Noise Ratio in NMR Imaging,” Magn Reson Med, vol. 3, no. 4, pp. 604–618, 1986, doi: 10.1002/mrm.1910030413.
[2]	J. R. Ashley and F. M. Palka, “Reflection Coefficient Measurement of Microwave Resonator {Q} Factors,” The Microwave Journal, pp. 35–39, Jun. 1971.
[3]	Luc Darrasse and Ghazi Kassab, “Quick Measurement of NMR-Coil Sensitivity with a Dual-Loop Probe,” Review of Scientific Instruments, vol. 64, no. 7, pp. 1841–1844, Jul. 1993.
[4]	Axel Haase et al., “NMR Probeheads for In Vivo Applications,” Concepts in Magnetic Resonance, vol. 12, no. 6, pp. 361–388, 2000.

## Contributors
Nicola De Zanche
Giulio Giovannetti

## Licenses
Layouts and other CAD files are licensed under the [CERN-OHL-W 2.0 license](), version 2.0 or any later version.

All other original content in this repository (including this README file) is licensed under a [Creative Commons Attribution-NoDerivatives 4.0 International License]().
