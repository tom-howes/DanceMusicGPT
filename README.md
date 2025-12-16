# HouseMusicGPT
Building a Transformer and training it on MIDI datasets using REMI+ tokenization to generate house music loops 

Activity Log:

**Day 1**

Exploration
- Tokenization
Read papers on REMI (Huang and Yang 2020) and REMI+ (Figaro 2023) to gain a background understanding of music tokenization techniques. Revamped MIDI involves tokenization of MIDI files into representations of notes as successions of Pitch, Velocity and Duration tokens, and time with Bar and Position tokens. Remi+ is an extension of REMI that adds program tokens before pitch ones to deal with multi-track symbolic musical sequences. Remi+ is ideal for this project as house music typically combines bass, synths and drums and various samples.

- Data
Lakh MIDI database - Colin Raffel. "Learning-Based Methods for Comparing Sequences, with Applications to Audio-to-MIDI Alignment and Matching". PhD Thesis, 2016.
Messy metadata and mix of genres - a lot of songs have lyrics
MIDI tracks - Found some free MIDI tracks on various online forums that replicate popular dance songs in simple MIDI format
