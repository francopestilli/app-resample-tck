[![Run on Brainlife.io](https://img.shields.io/badge/Brainlife-bl.app.124-blue.svg)](https://doi.org/10.25663/brainlife.app.124)

# app-resample-tck

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Resamples the streamlines of a .tck tractogram to a new step size (mm) or a fixed number of points per streamline with DIPY.**

Loads the tractogram with nibabel and resamples each streamline with dipy set_number_of_points, either to floor(length/step) points for a given step size or to a fixed number of points, and saves a new .tck. Use it to harmonise streamline sampling before segmentation or comparison methods that expect a given step size or point count.

| | |
|---|---|
| 📥 **Inputs** | `neuro/track/tck` |
| 📤 **Outputs** | `neuro/track/tck` |
| 🐳 **Container** | `brainlife/dipy:0.14` |
| ⚙️ **Resources** | 1 CPUs · 0.17 h walltime |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.124](https://doi.org/10.25663/brainlife.app.124) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `0` | `neuro/track/tck` | yes | tractogram |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `tck` | `neuro/track/tck` | resampled tractogram |

<details>
<summary><b>⚙️ Parameters</b> (2)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `type` | enum |  | Resampling can be done either by setting the new step size (in mm) or the new number of points. Tell which option you want to use. Options: `step_size`, `nb_points`. |
| `new_param` | number |  | Set the step size OR the number of points, depending on your choice above |

</details>

📚 **References used by this App:**
- Tournier J-D, Calamante F, Connelly A. MRtrix: Diffusion tractography in crossing fiber regions. Int J Imaging Syst Technol 22:53-66 (2012). [doi:10.1002/ima.22005](https://doi.org/10.1002/ima.22005)
- Avesani P et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. Sci Data 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

<!-- brainlife-app:end -->

This App resamples the streamlines of a tractogram (in tck format) with a given step size or, alternatively, with a given number of points.

### Authors
- Giulia Bertò (giulia.berto.4@gmail.com)

### Funding Acknowledgement
We kindly ask that you acknowledge the funding below in your publications and code reusing this code. \
[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-1636893](https://img.shields.io/badge/NSF_BCS-1636893-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-AOC-1916518](https://img.shields.io/badge/NSF_AOC-1916518-blue.svg)](https://nsf.gov/awardsearch/showAward?AWD_ID=1916518)

### Citation
We kindly ask that you cite the following article when publishing papers and code using this code. 

Avesani, P., McPherson, B., Hayashi, S. et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. Sci Data 6, 69 (2019). [https://doi.org/10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Running the app
### On [Brainlife.io](http://brainlife.io/) 
You can submit this App online at https://doi.org/10.25663/brainlife.app.124 via the “Execute” tab.

Input: \
A tractogram in tck format. Resampling can be done either by setting the new step size (in mm) or the new number of points. 

Output: \
The new resampled tractogram.

### Running locally
1. git clone this repo.
2. Inside the cloned directory, create `config.json` with something like the following content with paths to your input files:
```
{
    "track": "./track.tck",
    "type": "step_size",
    "new_param": 0.625
}
```
3. Launch the App by executing `main`.
```
./main
```

#### Dependencies
This App only requires [singularity](https://sylabs.io/singularity/) to run.

#### MIT Copyright (c) 2019 Giulia Bertò
