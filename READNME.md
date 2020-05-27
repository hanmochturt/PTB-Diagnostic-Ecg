# PTB Diagnostic ECG  classification based on LSTM

## Data Description
The ECGs in this collection were obtained using a non-commercial, PTB prototype recorder with the following specifications:
> - 16 input channels, (14 for ECGs, 1 for respiration, 1 for line voltage)
> - Input voltage: ±16 mV, compensated offset voltage up to ± 300 mV
> - Input resistance: 100 Ω (DC)
> - Resolution: 16 bit with 0.5 μV/LSB (2000 A/D units per mV)
> - Bandwidth: 0 - 1 kHz (synchronous sampling of all channels)
> - Noise voltage: max. 10 μV (pp), respectively 3 μV (RMS) with input short circuit
> - Online recording of skin resistance
> - Noise level recording during signal collection

The database contains 549 records from 290 subjects (aged 17 to 87, mean 57.2; 209 men, mean age 55.5, and 81 women, mean age 61.6; ages were not recorded for 1 female and 14 male subjects). Each subject is represented by one to five records. There are no subjects numbered 124, 132, 134, or 161. Each record includes 15 simultaneously measured signals: the conventional 12 leads (i, ii, iii, avr, avl, avf, v1, v2, v3, v4, v5, v6) together with the 3 Frank lead ECGs (vx, vy, vz). Each signal is digitized at 1000 samples per second, with 16 bit resolution over a range of ± 16.384 mV. On special request to the contributors of the database, recordings may be available at sampling rates up to 10 KHz.

Within the header (.hea) file of most of these ECG records is a detailed clinical summary, including age, gender, diagnosis, and where applicable, data on medical history, medication and interventions, coronary artery pathology, ventriculography, echocardiography, and hemodynamics. The clinical summary is not available for 22 subjects. The diagnostic classes of the remaining 268 subjects are summarized below:

<table>
   <tr>
      <td>Diagnostic class</td>
      <td>Number of subjects</td>
   </tr>
   <tr>
      <td>Myocardial infarction</td>
      <td>148</td>
   </tr>
   <tr>
      <td>Cardiomyopathy/Heart failure</td>
      <td>18</td>
   </tr>
   <tr>
      <td>Bundle branch block</td>
      <td>15</td>
   </tr>
   <tr>
      <td>Dysrhythmia</td>
      <td>14</td>
   </tr>
   <tr>
      <td>Myocardial hypertrophy</td>
      <td>7</td>
   </tr>
   <tr>
      <td>Valvular heart disease</td>
      <td>6</td>
   </tr>
   <tr>
      <td>Myocarditis</td>
      <td>4</td>
   </tr>
   <tr>
      <td>Miscellaneous</td>
      <td>4</td>
   </tr>
   <tr>
      <td>Healthy controls</td>
      <td>52</td>
   </tr>
</table>

## Model
Detailed code show in ```model.ipynb```.
Use multi-layer LSTMs.

## Result
Use the model to train 10 epochs, 20 epochs, 30 epochs, the corresponding result is __92.1% 94.2% 95.8%__.

## References
- Bousseljot, R.; Kreiseler, D.; Schnabel, A. Nutzung der EKG-Signaldatenbank CARDIODAT der PTB über das Internet. Biomedizinische Technik, Band 40, Ergänzungsband 1 (1995) S 317

- Kreiseler, D.; Bousseljot, R. Automatisierte EKG-Auswertung mit Hilfe der EKG-Signaldatenbank CARDIODAT der PTB. Biomedizinische Technik, Band 40, Ergänzungsband 1 (1995) S 319


