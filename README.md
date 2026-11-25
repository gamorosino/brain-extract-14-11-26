<h1 align="center">brain-extract-14-11-26</h1>

<p align="center">
  Brain extraction (skull-stripping) using FSL BET
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/brainlife.app.1000"><img src="https://img.shields.io/badge/Brainlife-brainlife.app.1000-blue.svg" alt="Run on brainlife.io"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Brain extraction (skull-stripping) using FSL BET**

Runs FSL bet on the T1w image with the chosen fractional intensity threshold and optional robust centre estimation (-R) and bias field/neck cleanup (-B), via run_bet.sh and brain_extract.py. The repository has no main file, so brainlife.io cannot start the App as registered, and no container is specified.

| | |
|---|---|
| **Inputs** | `neuro/anat/t1w` |
| **Outputs** | `neuro/anat/t1w` |
| **Run it** | [doi.org/10.25663/brainlife.app.1000](https://doi.org/10.25663/brainlife.app.1000) |

#### Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `t1w` | `neuro/anat/t1w` | yes | Input T1-weighted NIfTI volume to skull-strip. |

#### Outputs

| Output | Datatype | Description |
|---|---|---|
| `t1_brain` | `neuro/anat/t1w` | Brain-extracted (skull-stripped) T1w volume produced by FSL BET. |

<details>
<summary><b>Parameters</b> (3)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `frac` | number | `0.5` | BET fractional intensity threshold (0–1). Lower values give a larger brain estimate. |
| `robust` | boolean | `false` | Use BET's robust brain centre estimation (-R). |
| `bias_neck_cleanup` | boolean | `false` | Bias field and neck clean-up (-B). |

</details>

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

Open the App at [doi.org/10.25663/brainlife.app.1000](https://doi.org/10.25663/brainlife.app.1000), choose `neuro/anat/t1w` from your project, set the parameters and press **Execute**. The results are saved to your project as `neuro/anat/t1w`.

### Locally

You need [`jq`](https://jqlang.github.io/jq/).

1. Clone this repository.
2. Create `config.json` with the paths to your inputs and the parameters:

   ```json
   {
       "t1": "/path/to/t1w/t1",
       "frac": 0.5,
       "robust": false,
       "bias_neck_cleanup": false
   }
   ```

3. Run `./main`.

## Citing

If you use this App, please cite it, the software it builds on and brainlife.io:

- brain-extract-14-11-26. brainlife.io App. [doi:10.25663/brainlife.app.1000](https://doi.org/10.25663/brainlife.app.1000)
- Jenkinson et al. FSL. *NeuroImage* 62:782-790 (2012). [doi:10.1016/j.neuroimage.2011.09.015](https://doi.org/10.1016/j.neuroimage.2011.09.015)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

Maintained by [@gamorosino](https://github.com/gamorosino).
