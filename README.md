# Real-time Voice Activity Detection (VAD) and Transcription with Openai Whisper
- Author: Mr. Jack
- Date: 01 Nov 2025

This project provides real-time voice activity detection with automatic transcription capabilities. It can detect speech segments and transcribe them using Whisper.

## Version Information

- Current Version: 1.1
  - Real-time VAD
  - 100% Locally
  - Automatic transcription using Whisper
  - Audio recording and saving
  
- Coming in Version 1.2:
  - Speaker diarization features
  - Support for both pyannote.audio and local diarization
  - Speaker identification in transcripts
  - Enhanced audio processing pipeline

## Key Features (v1.1)

- Real-time Voice Activity Detection (VAD) using WebRTC
- Accurate transcription using OpenAI's Whisper model
- Audio recording and saving capability
- Real-time transcription display
- Export transcripts with timestamps
- Easy-to-use Jupyter notebook interface

## Upcoming Features (v1.2)

- Speaker diarization with pyannote.audio (or local option)
- Enhanced transcripts with speaker labels

## Prerequisites

### System Requirements
- Python 3.8 or higher
- ffmpeg (for audio processing)
- MacOS: Install ffmpeg using homebrew:
  ```bash
  brew install ffmpeg
  ```

### Python Dependencies
Install the required Python packages:

```bash
pip install numpy sounddevice webrtcvad soundfile
pip install openai-whisper
pip install torch torchaudio
```

## Usage

1. Open `realtime_vad_transcription.ipynb` in Jupyter Notebook or VS Code
2. Run the installation cells to install required packages
3. Run the imports cell
4. Run the class definition cells in order:
   - RealtimeVAD
   - TranscriptionWorker
5. Create and start the VAD instance

The system will:
- Record audio in real-time
- Detect speech segments
- Identify speakers
- Transcribe speech
- Save results to a transcript file
- Save the audio recording

## Output

- Console output shows real-time transcriptions with speaker IDs
- Transcript file (default: `meeting_transcript.txt`) contains:
  ```
  [0.5s -> 2.3s] SPEAKER_1: First speaker's transcribed text
  [2.5s -> 4.1s] SPEAKER_2: Second speaker's response
  ```
- Audio recording saved as WAV file (default: `recording.wav`)

## Troubleshooting

1. If audio recording fails:
   - Check if your microphone is properly connected
   - Verify sounddevice can access your microphone
   - Run `python -m sounddevice` to list available devices

2. For transcription issues:
   - Ensure Whisper model is downloaded (happens automatically first run)
   - Check if ffmpeg is installed correctly

## Notes

- The system uses a 16kHz sample rate for compatibility with WebRTC VAD
- Speech detection sensitivity can be adjusted via `vad_sensitivity` parameter
- Speaker similarity threshold can be tuned in LocalDiarizer
- Transcription uses Whisper's "base" model by default

## License

This project is licensed under MIT License - see the LICENSE file for details.
