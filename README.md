# Preprocessed Neural Radiance Fields: PP-NeRF

## Description
PP-NeRF is a novel framework designed to generate new perspectives of intricate scenes from sparse data. By leveraging Neural Radiance Fields (NeRF) as the foundation and introducing preprocessing techniques, we achieve superior 3D scene reconstruction, particularly for low-resolution images.

## Key Features
- **Compressed NeRF Architecture**: A streamlined implementation that maintains rendering quality while reducing computational overhead
- **Image Preprocessing Pipeline**: Combines high/low-pass filters with background masking
- **Model-Agnostic Design**: Compatible with various NeRF implementations, including NVIDIA's Instant-NGP
- **Superior Detail Reconstruction**: Particularly effective for architectural features and textures

## Technical Implementation

### Compressed NeRF Architecture
- 5 hidden layers (compared to original 10)
  - 4 fully-connected ReLU layers (128 filters)
  - 1 fully-connected ReLU layer (68 filters)
- Adam optimizer with learning rate 5e-3
- 32 depth samples per ray
- Training time: ~30 minutes (vs. several hours for original NeRF)

### Preprocessing Pipeline
1. Dataset Collection
   - Support for various input formats
   - Tested on Lego and Gerrard Hall datasets

2. Image Preprocessing
   - Background masking/removal
   - Edge enhancement using high-pass filters
   - Selective Gaussian blurring
   - Custom filter combinations

3. Camera Parameter Generation
   - Pinhole camera model implementation
   - Estimation of focal length, distortion parameters, rotation, and translation

## Results
- Successfully reconstructed complex architectural scenes
- Improved detail preservation in low-resolution inputs
- Enhanced edge and texture reconstruction
- Significant reduction in training time

## Future Work
- Expansion of preprocessing techniques
- Adaptation for in-the-wild photographs
- Integration with varying lighting conditions
- Development of stronger 3D priors

## Authors
- Kushagra Chitkara (kchitkar@mit.edu)
- Christian Aagnes (caagnes@mit.edu)


## References
1. NeRF: Representing Scenes as Neural Radiance Fields for View Synthesis
2. Instant Neural Graphics Primitives with a Multiresolution Hash Encoding
3. Structure-from-Motion Revisited
4. COLMAP

## License
MIT License - See LICENSE file for details
