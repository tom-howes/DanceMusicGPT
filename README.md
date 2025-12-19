# DanceMusicGPT
Building a Transformer and training it on MIDI datasets using REMI+ tokenization to generate house music loops 

Activity Log:

**Day 1**

Exploration
- Tokenization
Read papers on REMI (Huang and Yang 2020) and REMI+ (Figaro 2023) to gain a background understanding of music tokenization techniques. Revamped MIDI involves tokenization of MIDI files into representations of notes as successions of Pitch, Velocity and Duration tokens, and time with Bar and Position tokens. Remi+ is an extension of REMI that adds program tokens before pitch ones to deal with multi-track symbolic musical sequences. Remi+ is ideal for this project as house music typically combines bass, synths and drums and various samples.

Data
- Lakh MIDI database - Colin Raffel. "Learning-Based Methods for Comparing Sequences, with Applications to Audio-to-MIDI Alignment and Matching". PhD Thesis, 2016. Messy metadata and mix of genres.
- MIDI tracks - Found some free MIDI tracks on various online forums that replicate popular dance songs in simple MIDI format

Ended up going for free MIDI tracks for initial testing - pivoting to dance music as it is hard to find house MIDI tracks

**Day 2**

Tokenizer set up and tweaks
 - Set up REMIplus tokenizer, required a lot of bug fixing and config tweaking. Ended up removing chords and prepending all programs (instruments) to one stream to generate 1 multi-track midi file
GPT Research
 - Read papers on Transformer-Decoder (Liu et al 2018) and Deeper Self attention (Al-Rfou et al), decided to run some baseline tests on GPT-2 to give my model something a benchmark to compare to
GPT-2 set up
 - Used GPT-2 huggingface transformer, configuring with ~5m parameters (context window = 512, num embed = 256, layers = 6, attention heads = 8)
Training
 - Initially trained for 10 epochs with stride length of 256 (4-5000 data samples) for faster training (~6 min on T4 GPU)
   - Final training loss was ~0.02
   - Generated midi file was 500 tokens (2 seconds) and it successfully created 1 chord with some echo
 - Next trained for 50 epochs, halved LR and doubled batch size (~35 min on T4 GPU)
   - Final training loss = 0.013
   - Ran into bug when generating will investigate tomorrow



