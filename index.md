# Adversarial Example Demo

Supplementary material containing a selection of benign, adversarial, and noisy data employed in our [*paper*]().

For each sample, we include the word error rate (WER) as an accuracy metric and the segmental signal-to-noise ratio (SNR<sub>seg</sub>) as a quality noise metric. An SNR<sub>seg</sub> exceeding 0 dB indicates a stronger signal presence compared to noise. These samples are sourced from the [*Librispeech*](https://www.openslr.org/12) corpus dataset.

As outlined in our paper we investigated three types of training regimes, resulting in three different models, respectively :

1. **Baseline (no augmentation):** This model serves as our control of the clean dataset without any form of augmentation. 
    This baseline establishes the standard level of performance for each model under ideal acoustic conditions.
    
2. **Augmentation with speed variations:** During the training of the second model temporal variability was introduced into the training data by applying speed perturbations. 
    These augmentations simulate natural variations in speech tempo, which can occur due to speaker differences or recording conditions.
    
3. **Augmentation with speed variations, background noise, and reverberation:** The third model is trained with both background noises and reverberations, in addition to speed variations. 
    This combination aims to mimic more challenging and realistic acoustic environments that ASR systems may encounter in real-world applications.

The key takeaway from the following samples is that models trained with augmentation methods tend to be more robust against adversarial attacks. This robustness is demonstrated by two main observations:

- **Higher WER:** A model is considered more robust if it produces a higher WER when using the target transcription as the reference. This means that the adversarial attack is less successful in forcing the model to recognize the target transcription.
- **Lower SNR<sub>seg</sub> values:**​ Models trained with augmentation seem to require greater noise to create effective adversarial examples.

Please note that the adversarial samples are crafted per model. In the following, we report the WER and SNR<sub>seg</sub> for the adversarial sample for each model, using the seq2seq model architecture described in our paper. However, we only play the adversarial example generated with respect to model 3 (augmentation with speed variations, background noise, and reverberation).

### Experiments for the C&W attack.
###### Sample 1 
<pre>
Benign transcription:       	    <em>THEY OF COURSE MUST ALL BE ALTERED</em>
Target Adversarial transcription:   <em>LOOK AT THAT HE HELD OUT HIS HAND</em>
Adversarial transcription model 1:  <em>LOOK AT THAT HE HELD OUT HIS HAND</em>
Adversarial transcription model 2:  <em>LOOK AT THAT HE HELD OUT HIS HAND</em>
Adversarial transcription model 3:  <em>LOOK AT THAT HE'LL BE OUT OF IT</em>
</pre> &nbsp;
**Benign**:                    **Benign + Noise**: SNR<sub>seg</sub>= -4.81  
[**1**: *WER*=00.00],                 [**1**: *WER*=71.43]  
[**2**: *WER*=00.00],                 [**2**: *WER*=57.14]  
[**3**: *WER*=00.00],                 [**3**: *WER*=14.29]  
<audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/8455-210777-0066.wav" type="audio/wav" />
</audio>
 <audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/8455-210777-0066_benign_noise.wav" type="audio/wav" />
</audio>
**C&W adversarial**:  
[**1**: *WER*=00.00, SNR<sub>seg</sub>=24.47]  
[**2**: *WER*=00.00, SNR<sub>seg</sub>=18.84]  
[**3**: *WER*=50.00, SNR<sub>seg</sub>=15.93]  
<audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/8455-210777-0066_cw_26022.wav" type="audio/wav" />
</audio>
###### Sample 2
<pre>
Benign transcription:               <em>TO THEIR SORROW THEY WERE SOON UNDECEIVED</em>
Target Adversarial transcription:   <em>ONE COULD HARDLY HOPE FOR ANY UPON SO DRY A DAY</em>
Adversarial transcription model 1:  <em>ONE COULD HARDLY HOPE FOR ANY UPON SO DRY A DAY</em>
Adversarial transcription model 2:  <em>ONE COULD HARDLY HOPE FOR ANY SLEEP A DAY</em>
Adversarial transcription model 3:  <em>ONE COULD HARDLY HOPE FOR ANY ONE WHO HAD</em>
</pre> &nbsp;
**Benign**:                    **Benign + Noise**: SNR<sub>seg</sub>= 1.34  
[**1**: *WER*=00.00],                 [**1**: *WER*=57.14]  
[**2**: *WER*=00.00],                 [**2**: *WER*=00.00]  
[**3**: *WER*=00.00],                 [**3**: *WER*=0.00]  
<audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/7729-102255-0034.wav" type="audio/wav" />
</audio>
 <audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/7729-102255-0034_benign_noise.wav" type="audio/wav" />
</audio>
**C&W adversarial**:  
[**1**: *WER*=00.00, SNR<sub>seg</sub>=22.20]  
[**2**: *WER*=27.27, SNR<sub>seg</sub>=17.04]  
[**3**: *WER*=45.45, SNR<sub>seg</sub>=04.13]  
<audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/7729-102255-0034_cw_26022.wav" type="audio/wav" />
</audio>
###### Sample 3
<pre>
Benign transcription:       	    <em>BUT YOU KNOW MORE ABOUT THAT THAN I DO SIR</em>
Target Adversarial transcription:   <em>YES MY DEAR WATSON I HAVE SOLVED THE MYSTERY</em>
Adversarial transcription model 1:  <em>YES MY DEAR WATSON I HAVE SOLVED THE MYSTERY</em>
Adversarial transcription model 2:  <em>YES MY DEAR ROGER  I HAVE THE MYSTERY</em>
Adversarial transcription model 3:  <em>YES MY DEAR CHILD I AM AFRAID OF THE ELEMENTS</em>
</pre> &nbsp;
**Benign**:                    **Benign + Noise**: SNR<sub>seg</sub>= -0.41  
[**1**: *WER*=00.00],                 [**1**: *WER*=30.00]  
[**2**: *WER*=00.00],                 [**2**: *WER*=10.00]  
[**3**: *WER*=00.00],                 [**3**: *WER*=10.00]  
<audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/2094-142345-0055.wav" type="audio/wav" />
</audio>
 <audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/2094-142345-0055_benign_noise.wav" type="audio/wav" />
</audio>
**C&W adversarial**:  
[**1**: *WER*=00.00, SNR<sub>seg</sub>=25.78]  
[**2**: *WER*=22.22, SNR<sub>seg</sub>=23.94]  
[**3**: *WER*=55.56, SNR<sub>seg</sub>=22.30]  
<audio style="width:320px" controls="controls">
	<source src="audio_clips/c_w/2094-142345-0055_cw_26022.wav" type="audio/wav" />
</audio>
