# personalized-hearing-aid
Audiogram-tuned hearing assistance prototype in Python. Real-time multi-band EQ + compressor/limiter for wired mic/headphone setups. Adjustable to your own hearing profile. Hobby project, not a medical device. Read safety notes before running.

# DIY Hearing Aid Prototype

A real-time audio processing pipeline that boosts specific frequency 
ranges based on a personal audiogram, built as a hobbyist alternative 
to understand how hearing aids work, not as a replacement for a 
clinically fitted device.

## How it works
Microphone input is split into frequency bands, each boosted according 
to a gain curve derived from audiogram thresholds (using a simplified 
half-gain rule), then passed through a compressor and hard limiter 
before output — so loud sounds aren't amplified as aggressively as 
quiet ones.

## Before you run this
- This is a hobby project, **not a medical-grade hearing aid**. It has 
  not been clinically validated.
- Use **wired** headphones/earbuds only — Bluetooth latency makes the 
  audio noticeably delayed and unpleasant.
- Start at low system volume. The limiter caps output gain, but you 
  should still ease in.
- If you have access to an audiologist, get any gain curve you use 
  sanity-checked before relying on this for daily use.

## Setup
pip install -r requirements.txt
python hearing_aid.py

## Customize for your own audiogram
Edit the `AUDIOGRAM` dictionary near the top of `hearing_aid.py` with 
your own dB HL thresholds per frequency.
