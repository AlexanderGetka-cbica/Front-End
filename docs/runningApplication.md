# Running the Application

**Note** the `${fets_root_dir}` from [Setup](./setup.md#set-up-the-environment).

## Application Path

```bash
cd ${download_location}
./squashfs-root/usr/bin/FeTS # launches application
```
## Inference

<p align="center">
    <img src="https://github.com/FETS-AI/Front-End/blob/master/docs_sources/images/fets_inference.png?raw=true" />
</p>

- Ensure the data has been pre-processed and is organized in the format described above.
- Click to the **Segmentation** tab in the UI
- Set up the inputs:
  - Select the input directory, which would be `/data_folder` in the above illustration
- From the "Algorithms" group, select the appropritate model (for Phase-1, we are providing pre-trained models using the 3DResUNet architecture):
  - Skull Stripping 
  - Brain Tumor Segmentation
- Select if you want to run the inference on GPU or CPU
- Click "Fusion + Save" to start
- Use the drawing tools provided in the "Drawing" tab for corrections and save the final segmentation.
- **Note**: 
  - For CPU, a run-time requirement of at least 48GB of RAM would be needed
  - For GPU, at least 11GB of dedicated VRAM would be needed

## Training

<p align="center">
    <img src="https://github.com/FETS-AI/Front-End/blob/master/docs_sources/images/fets_training.png?raw=true" />
</p>

- Ensure the data has been pre-processed and is organized in the format described above.
  - Note that there should be **only 1** file that ends in `_seg.nii.gz`, as this will be used for training the Brain Tumor Segmentation model
- Click to the **Segmentation** tab in the UI
- Set up the inputs:
  - Select the input directory, which would be `/data_folder` in the above illustration
  - Type the correct common collaboration name, which would be `${collaborator_common_name}`
- For Phase-1, we currently support training on the 3DResUNet architecture for Brain Tumor Segmentation.
- Select if you want to run the inference on GPU or CPU
- Click "Train + Save" to start