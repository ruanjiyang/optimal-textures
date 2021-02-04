# Optimal textures


An implementation of the texture generation algorithm proposed in [Optimal Textures: Fast and Robust Texture Synthesis and Style Transfer through Optimal Transport](https://arxiv.org/abs/2010.14702).

### Example output

#### Original image
![original](demo/original.jpg)

#### Generated images
![generated_1](demo/generated_1.png)
![generated_2](demo/generated_2.png)
![generated_3](demo/generated_3.png)

## Run 

* In order to used pre-trained decoder weights, set up a directory containing `.pth` weight files with the form
```bash
Relu1_1_decoder_state.pth
Relu2_1_decoder_state.pth
Relu3_1_decoder_state.pth
Relu4_1_decoder_state.pth
Relu5_1_decoder_state.pth
```
If you want to train your decoders on your own image instead, this directory will be used to store the generated weights.

* Set layer-specific parameters like the number of epoch and the learning rate for the decoders training phase, as well as iteration parameters in the dictionary `observed_layers` at the bottom of the file `decoders.py`.

* Run the generation process with

```bash
python run.py path_to_source_image path_to_decoder_states_directory -o output_path -n n_passes -t train
```



## Requirements
* Python 3
* torch
