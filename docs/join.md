---
layout: page
title: Join the Challenge
permalink: /join/
poster_img: /assets/images/home/icon-submit.svg
poster_alt: TODO! A description of the poster image
---
# Join the challenge!

## Overview

The PSST Challenge consists of two tasks:

- In [Task A: Phoneme Recognition](#task-a-phoneme-recognition), we ask participants to phonemically transcribe speech from recordings of people with aphasia
- In [Task B: Correctness](#task-b-correctness), we ask people to determine whether a target word is both present and correctly pronounced in the same recordings

Contestants may focus on either Task A or B, or they may take on the entire challenge. Although Task B is dependent on the output of Task A, you are most welcome to use our [baseline speech recognition model](https://github.com/PSST-Challenge/psstbaseline) for the foundation of your system.

## Challenge Data

### Access to the data
We've created a unique data set for phonemic ASR, derived from the recordings in the English AphasiaBank—for the challenge. Please fill out [this form](https://docs.google.com/forms/d/e/1FAIpQLScwAC3j7NQ2giyFSjrNen6NhmSbnHqdxS915ftZDBRi2SHQtQ/viewform) to gain access to the data.

We have prepared a [set of scripts and utilities](https://github.com/PSST-Challenge/psstdata) for downloading and using the data, once you have received access permissions.

#### Notes on Usage

All users of this dataset must follow the appropriate AphasiaBank protocols for data management, and is intended for use solely as part of the PSST challenge. It must not be re-distributed, shared, or repurposed without permission.

Furthermore, we ask that users of this dataset cite both AphasiaBank and us in any resulting publications, as follows:

1. Macwhinney, B., Fromm, D., Forbes, M., & Holland, A. (2011). AphasiaBank: Methods for Studying Discourse. Aphasiology, 25(11), 1286–1307. https://doi.org/10.1080/02687038.2011.589893
2. Gale, R., Fleegle, M., Bedrick, S., & Fergadiotis, G. (2022). [Dataset and tools for the PSST Challenge on Post-Stroke Speech Transcription](https://github.com/PSST-Challenge/psstdata) (Version 1.0.0) [Data set]. https://doi.org/10.5281/zenodo.6326002


### A quick look at the data

To get started with the data [using our toolkit](https://github.com/PSST-Challenge/psstdata), have a look at this short example, where we simply print data from the first four records in the corpus:

```python
import psstdata

data = psstdata.load()

for utterance in data.train[:4]:
    
    # The key ingredients
    utterance_id = utterance.utterance_id
    transcript = utterance.transcript
    correctness = "Y" if utterance.correctness else "N"
    filename = utterance.filename

    print(f"{utterance_id:26s} {transcript:26s} {correctness:11s} {filename}")
```

Which produces:

```
# utterance_id             transcript                 correctness  filename

ACWT02a-BNT01-house        HH AW S                    Y            audio/bnt/ACWT02a/ACWT02a-BNT01-house.wav
ACWT02a-BNT02-comb         K OW M                     Y            audio/bnt/ACWT02a/ACWT02a-BNT02-comb.wav
ACWT02a-BNT03-toothbrush   T UW TH B R AH SH          Y            audio/bnt/ACWT02a/ACWT02a-BNT03-toothbrush.wav
ACWT02a-BNT04-octopus      AA S AH P R OW G P UH S    N            audio/bnt/ACWT02a/ACWT02a-BNT04-octopus.wav
```

These four fields (`utterance_id`, `transcript`, `correctness`, and `filename`) are the pieces you'll need for both challenge tasks. Transcripts are in [ARPAbet](https://en.wikipedia.org/wiki/ARPABET), and can be reliably tokenized using spaces as a separator (`phonemes`&nbsp;`=`&nbsp;`utterance.transcript.split(" ")`). For Task B, we provide an additional resource: [all the pronunciations we consider "correct"](https://github.com/PSST-Challenge/psstdata/blob/main/psstdata/assets/correctness.json) (more on that below). You can learn more about the `psstdata` tool on its [GitHub page](https://github.com/PSST-Challenge/psstdata), where you can also find a copy of the [README](https://github.com/PSST-Challenge/psstdata/blob/main/readme/train/README.md) provided with the data packs.


### Background on the PSST corpus

This dataset includes audio recordings and phonemic transcriptions of research participants with post-stroke aphasia, specifically their responses to two confrontation picture naming tests, the Boston Naming Test - Short Form (BNT-SF) and the Verb Naming Test (VNT). For more background on what aphasia is and the clinical context of this work, please visit our clinical background page. The audio data was sourced from the AphasiaBank database (MacWhinney et al., 2011), and participant first responses were selected, segmented, and transcribed by our team at Portland Allied Laboratories for Aphasia Technologies (PALAT).

## Task A: Phoneme Recognition

The primary task of this challenge (Task A) is to develop an automatic phoneme recognition (APR) system that accurately identifies the phonemes produced by people with aphasia and to present those phonemes as they are, rather than smoothed over to fit whatever real word the speaker may have intended. This task has important clinical applications, including automatic scoring of picture naming test responses (Task B).   


### Evaluation: Phoneme & Feature Error Rates (PER and FER)

Task A will be evaluated in terms of two metrics: phoneme error rate (PER) and feature error rate (FER), with the emphasis on the latter. PER is defined as the number of phoneme errors (edits, insertions, and substitutions) divided by the number of phonemes in the reference transcript. It is the standard metric for phoneme recognition, and without it we would have little perspective on the performance of the APR systems built for this challenge. However, we find PER to have particular weaknesses, which we attempt to overcome with the use of FER. FER is similar to PER, but instead of phoneme errors, we compute the number of errors in terms of [distinctive phonological features](https://en.wikipedia.org/wiki/Distinctive_feature). Without worrying too much about the theory behind phonological features, we want to emphasize this intuition: we're looking for speech recognizers that produce transcripts which *sound* closest to the truth.

Consider an example utterance where someone says /V&nbsp;AE&nbsp;N/&nbsp;&nbsp;("van"), but a speech recognizer predicts /F&nbsp;AE&nbsp;N/&nbsp;&nbsp;("fan"). In terms of PER, we find 1 error out of a target length of 3, so 1/3 is about 33%. Now let's say another speech recognizer predicts /K&nbsp;AE&nbsp;N/&nbsp;&nbsp;("can"), which has the same PER of 33%. However, we insist that /F/ is a preferable error to /K/, since it sounds closer. Phonological features can quantify the difference. Phonologically, /F/ and /V/ differ in one respect: the latter uses the voice while the former does not. Otherwise, they're both consonants produced with the lower lip against the upper teeth, and a steady stream of air (labiodental fricatives). Like /F/, /K/ is also unvoiced; however, is produced with the back of the tongue against the soft palate, and a sudden burst of air (velar plosive). In terms of phonological features, going from /V/ to /F/ is [-voice], while /V/ to /K/ is [-continuant, -voice, -anterior, -labial, +high]. So in this example, "fan" amounts to 1 feature rror while "can" totals 5. If our feature system utilizes 20 distinctive features per phoneme, the FER of "fan" is 1/60 (about 2%), while "can" is 5/60 (about 8%). 

If you've never studied phonology, this might seem like a lot. But rest assured that if you work on a speech recognizer, we'll provide the linguistic analysis. Soon we will provide tools to compute your WER and PER metrics, as well as a feature distance breakdown similar to the above.

## Task B: Correctness

Test how well the APR developed in Task A performs in a clinically relevant context. Task B is automatic binary scoring (correct vs. incorrect) of automatically transcribed picture naming responses. If the transcribed response contains the name of the picture, or one of its accepted alternative names, then the response is scored as correct.

### Correctness Data

To simplify the task, we provide a set of accepted “correct” pronunciations (e.g., send-mail, send-sendin’, etc.) are provided, since Task B will be evaluated in terms of response scoring agreement and assembling this dictionary is outside the scope of the present challenge. The dictionary can be retrieved from our [Python tool](https://github.com/PSST-Challenge) at `psstdata.ACCEPTED_PRONUNCIATIONS`, or in [json format](https://raw.githubusercontent.com/PSST-Challenge/psstdata/main/psstdata/assets/correctness.json).

The main challenge of Task B is distinguishing mispronunciations from APR errors. With an ideal APR (0% phoneme errors), a simple substring function would achieve about 99% accuracy on this task. (The other 1% is mostly part-of-speech errors—e.g. on the VNT, the verb "mail" is correct, but the noun "mailbox" is not—and probably not worth pursuing during the challenge.) Conversely, if you're relying only on the 1-best transcript from an unreliable speech recognizer, you'll score poorly with little room to improve. 
For contestants taking on Task B without also working on Task B, we are sharing our [baseline speech recognizer](https://github.com/PSST-Challenge/psstbaseline), which first produces a matrix of per-frame, per-phone likelihoods prior to decoding into an ARPAbet transcript. 

### Evaluation
 
Task B will be evaluated in terms of metrics of classification performance. Specifically, we will use F1 to quantify how well automated scores obtained from APR transcriptions compare with our team’s scores obtained from manual transcriptions. 


## Tasks A & B: Submission

The file format for results submission for the two tasks is currently being finalized, and will be posted in the second week of March. We will also provide validation scripts that can be used before submitting your results, to ensure their compatibility with our evaluation process.
