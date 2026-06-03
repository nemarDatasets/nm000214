[![DOI](https://img.shields.io/badge/DOI-10.82901%2Fnemar.nm000214-blue)](https://doi.org/10.82901/nemar.nm000214)

# c-VEP dataset from Thielen et al. (2021)

c-VEP dataset from Thielen et al. (2021)

## Dataset Overview

- **Code**: Thielen2021
- **Paradigm**: cvep
- **DOI**: 10.34973/9txv-z787
- **Subjects**: 30
- **Sessions per subject**: 1
- **Events**: 1.0=101, 0.0=100
- **Trial interval**: (0, 0.3) s
- **Runs per session**: 5
- **File format**: gdf
- **Contributing labs**: MindAffect, Radboud University

## Acquisition

- **Sampling rate**: 512.0 Hz
- **Number of channels**: 8
- **Channel types**: eeg=8
- **Channel names**: Fpz, Iz, O1, O2, Oz, POz, T7, T8
- **Montage**: custom
- **Hardware**: Biosemi ActiveTwo
- **Reference**: CMS/DRL
- **Sensor type**: sintered Ag/AgCl active electrodes
- **Line frequency**: 50.0 Hz

## Participants

- **Number of subjects**: 30
- **Health status**: healthy
- **Age**: mean=25.0, min=19, max=62
- **Gender distribution**: female=17, male=13

## Experimental Protocol

- **Paradigm**: cvep
- **Number of classes**: 2
- **Class labels**: 1.0, 0.0
- **Trial duration**: 31.5 s
- **Study design**: Code-modulated visual evoked potentials BCI task where participants fixated on target cells in a calculator grid (offline) or keyboard layout (online) while all cells flashed with unique pseudo-random Gold code modulated bit-sequences
- **Feedback type**: none
- **Stimulus type**: visual
- **Stimulus modalities**: visual
- **Primary modality**: visual
- **Synchronicity**: synchronous
- **Mode**: offline
- **Training/test split**: False
- **Instructions**: Participants maintained fixation at the target cell which was cued in green for 1 s before trial onset. No feedback was given after trials in the offline experiment.

## HED Event Annotations

Schema: HED 8.4.0 | Browse: https://www.hedtags.org/hed-schema-browser

```
  1.0
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Label/intensity_1_0

  0.0
    ├─ Sensory-event
    ├─ Experimental-stimulus
    ├─ Visual-presentation
    └─ Label/intensity_0_0

```
## Paradigm-Specific Parameters

- **Detected paradigm**: cvep
- **Code type**: modulated Gold codes
- **Code length**: 126
- **Number of targets**: 20

## Data Structure

- **Trials**: 100
- **Blocks per session**: 5
- **Trials context**: per_subject (5 blocks × 20 trials each)

## Preprocessing

- **Data state**: raw
- **Preprocessing applied**: False

## Signal Processing

- **Classifiers**: template-matching, reconvolution, CCA
- **Feature extraction**: encoding model, event responses, spatio-temporal
- **Spatial filters**: CCA

## Cross-Validation

- **Method**: cross-validation
- **Folds**: 5
- **Evaluation type**: within_session, transfer_learning, zero_training

## Performance (Original Study)

- **High Communication Rates**: achieved in online spelling task

## BCI Application

- **Applications**: speller
- **Environment**: indoor
- **Online feedback**: False

## Tags

- **Pathology**: Healthy
- **Modality**: Visual
- **Type**: Research

## Documentation

- **DOI**: 10.1088/1741-2552/abecef
- **Associated paper DOI**: 10.1088/1741-2552/ab4057
- **License**: CC0-1.0
- **Investigators**: J Thielen, P Marsman, J Farquhar, P Desain
- **Senior author**: P Desain
- **Contact**: jordy.thielen@donders.ru.nl
- **Institution**: Radboud University
- **Department**: Donders Institute for Brain, Cognition and Behaviour
- **Country**: NL
- **Repository**: Radboud
- **Data URL**: https://doi.org/10.34973/9txv-z787
- **Publication year**: 2021
- **Funding**: NWO/TTW Takeoff Grant No. 14054; International ALS Association and Dutch ALS Foundation Grant Nos. ATC20610 and 2017-57
- **Ethics approval**: Approved by the local ethical committee of the Faculty of Social Sciences of Radboud University
- **Keywords**: brain–computer interface (BCI), electroencephalography (EEG), code-modulated visual evoked potentials (cVEPs), reconvolution, zero training, spread spectrum communication

## External Links

- **Source**: https://doi.org/10.34973/9txv-z787

## Abstract

Objective. Typically, a brain–computer interface (BCI) is calibrated using user- and session-specific data because of the individual idiosyncrasies and the non-stationary signal properties of the electroencephalogram (EEG). Therefore, it is normal for BCIs to undergo a time-consuming passive training stage that prevents users from directly operating them. In this study, we systematically reduce the training data set in a stepwise fashion, to ultimately arrive at a calibration-free method for a code-modulated visually evoked potential (cVEP)-based BCI to fully eliminate the tedious training stage. Approach. In an extensive offline analysis, we compare our sophisticated encoding model with a traditional event-related potential (ERP) technique. We calibrate the encoding model in a standard way, with data limited to a single class while generalizing to all others and without any data. In addition, we investigate the feasibility of the zero-training cVEP BCI in an online setting. Main results. By adopting the encoding model, the training data can be reduced substantially, while maintaining both the classification performance as well as the explained variance of the ERP method. Moreover, with data from only one class or even no data at all, it still shows excellent performance. In addition, the zero-training cVEP BCI achieved high communication rates in an online spelling task, proving its feasibility for practical use. Significance. To date, this is the fastest zero-training cVEP BCI in the field, allowing high communication speeds without calibration while using only a few non-invasive water-based EEG electrodes. This allows us to skip the training stage altogether and spend all the valuable time on direct operation. This minimizes the session time and opens up new exciting directions for practical plug-and-play BCI. Fundamentally, these results validate that the adopted neural encoding model compresses data into event responses without the loss of explanatory power compared to using full ERPs as a template.

## Methodology

The study compared four training regimes: (1) e-train: traditional ERP template-matching with data from all classes, (2) n-train: encoding model (reconvolution) with data from all n classes, (3) 1-train: encoding model with data from only one class while generating templates for all sequences, (4) 0-train: zero-training encoding model requiring no calibration data. Offline experiment: 30 participants completed 5 blocks of 20 trials each (100 trials total), with 31.5 s trials using a 4×5 calculator grid (n=20 symbols). Stimuli were luminance-modulated pseudo-random Gold codes (126-bit sequences, 2.1 s duration) presented on an iPad Pro at 60 Hz. Online experiment: 11 participants (9 analyzed) used a keyboard layout (n=29 symbols) with dynamic stopping rule for spelling tasks. EEG recorded at 512 Hz from 8 electrodes, preprocessed with 2-30 Hz Butterworth filtering and downsampled to 120 Hz. Classification used template-matching with reconvolution encoding model that decomposes responses to sequences into linear sums of individual event responses.

## References

Thielen, J. (Jordy), Pieter Marsman, Jason Farquhar, Desain, P.W.M. (Peter) (2023): From full calibration to zero training for a code-modulated visual evoked potentials brain computer interface. Version 3. Radboud University. (dataset). DOI: https://doi.org/10.34973/9txv-z787

Thielen, J., Marsman, P., Farquhar, J., & Desain, P. (2021). From full calibration to zero training for a code-modulated visual evoked potentials for brain–computer interface. Journal of Neural Engineering, 18(5), 056007. DOI: https://doi.org/10.1088/1741-2552/abecef

Ahmadi, S., Borhanazad, M., Tump, D., Farquhar, J., & Desain, P. (2019). Low channel count montages using sensor tying for VEP-based BCI. Journal of Neural Engineering, 16(6), 066038. DOI: https://doi.org/10.1088/1741-2552/ab4057

Notes

.. versionadded:: 0.6.0
Appelhoff, S., Sanderson, M., Brooks, T., Vliet, M., Quentin, R., Holdgraf, C., Chaumon, M., Mikulan, E., Tavabi, K., Hochenberger, R., Welke, D., Brunner, C., Rockhill, A., Larson, E., Gramfort, A. and Jas, M. (2019). MNE-BIDS: Organizing electrophysiological data into the BIDS format and facilitating their analysis. Journal of Open Source Software 4: (1896). https://doi.org/10.21105/joss.01896

Pernet, C. R., Appelhoff, S., Gorgolewski, K. J., Flandin, G., Phillips, C., Delorme, A., Oostenveld, R. (2019). EEG-BIDS, an extension to the brain imaging data structure for electroencephalography. Scientific Data, 6, 103. https://doi.org/10.1038/s41597-019-0104-8

---
Generated by MOABB 1.5.0 (Mother of All BCI Benchmarks)
https://github.com/NeuroTechX/moabb
