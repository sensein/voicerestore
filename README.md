# VoiceRestore: Universal Audio Quality Restoration

VoiceRestore is a cutting-edge speech restoration model designed to significantly enhance the quality of degraded voice recordings. Leveraging flow-matching transformers, this model excels at addressing a wide range of audio imperfections commonly found in speech, including background noise, reverberation, distortion, and signal loss.

Demo of audio restorations: [VoiceRestore](https://sparkling-rabanadas-3082be.netlify.app/)

Credits: This repository is based on the [E2-TTS implementation by Lucidrains](https://github.com/lucidrains/e2-tts-pytorch)

## Example
### Degraded Input: 

![Degraded Input](./imgs/degraded.png "Degraded Input")

Degraded audio (reverberation, distortion, noise, random cut):

**Note**: Adjust your volume before playing the degraded audio sample, as it may contain distortions.

https://github.com/user-attachments/assets/0c030274-60b5-41a4-abe6-59a3f1bc934b

---
### Restored (steps=32, cfg=1.0):

![Restored](./imgs/restored.png "Restored")

Restored audio - 32 steps, strength 1.0:


https://github.com/user-attachments/assets/633bc81c-8a52-477f-9f3a-eb51b907a7f9


---
### Ground Truth:

![Ground Truth](./imgs/ground_truth.png "Ground Truth")

---
## Key Features

- **Universal Restoration**: The model can handle any level and type of voice recording degradation. Pure magic.  
- **Easy to Use**: Simple interface for processing degraded audio files.
- **Pretrained Model**: Includes a 301 million parameter transformer model with pre-trained weights.

---
## Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/YourUsername/VoiceRestore.git
   cd VoiceRestore
   ```

2. Install dependencies:
   ```bash
   pip install torch torchaudio jaxtyping einops x-transformers torchdiffeq gateloop-transformer
   ```

3. Download the [pre-trained model](https://drive.google.com/drive/folders/1uBJNp4mrPJQY9WEaiTI9u09IsRg1lAPR?usp=sharing) and place it in the `checkpoints` folder.

4. Run a test restoration:
   ```bash
   python audio_restoration_model.py
   ```
   This will process `test_input.wav` and save the result as `test_output.wav`.

## Usage

To restore your own audio files:

```python
from audio_restoration_model import VoiceRestoreModel

model = VoiceRestoreModel()
restored_audio = model.forward(input_audio, steps=32, cfg_strength=1.0)
```



## Model Details

- **Architecture**: Flow-matching transformer
- **Parameters**: 301 million
- **Input**: Degraded speech audio (various formats supported)
- **Output**: Restored high-quality speech audio

## Limitations and Future Work

- Current model is optimized for speech; may not perform optimally on music or other audio types.
- Ongoing research to improve performance on extreme degradations.
- Future updates may include real-time processing capabilities.

## Citation

If you use VoiceRestore in your research, please cite our paper:

```
@article{kirdey2024voicerestore,
  title={VoiceRestore - Flow-Matching Transformers for Universal Audio Quality Restoration},
  author={Kirdey, Stanislav},
  journal={arXiv preprint arXiv:2024.XXXXX},
  year={2024}
}
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Based on the [E2-TTS implementation by Lucidrains](https://github.com/lucidrains/e2-tts-pytorch)
- Special thanks to the open-source community for their invaluable contributions.
