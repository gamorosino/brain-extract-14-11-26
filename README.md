# brain-extract-14-11-26

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Brain extraction (skull-stripping) using FSL BET**

Runs FSL bet on the T1w image with the chosen fractional intensity threshold and optional robust centre estimation (-R) and bias field/neck cleanup (-B), via run_bet.sh and brain_extract.py. The repository has no main file, so brainlife.io cannot start the App as registered, and no container is specified.

| | |
|---|---|
| 📥 **Inputs** | `neuro/anat/t1w` |
| 📤 **Outputs** | `neuro/anat/t1w` |
| 🔗 **Run it** | [doi.org/10.25663/brainlife.app.1000](https://doi.org/10.25663/brainlife.app.1000) |

#### 📥 Inputs

| Input | Datatype | Required | Description |
|---|---|---|---|
| `t1w` | `neuro/anat/t1w` | yes | Input T1-weighted NIfTI volume to skull-strip. |

#### 📤 Outputs

| Output | Datatype | Description |
|---|---|---|
| `t1_brain` | `neuro/anat/t1w` | Brain-extracted (skull-stripped) T1w volume produced by FSL BET. |

<details>
<summary><b>⚙️ Parameters</b> (3)</summary>

| Parameter | Type | Default | Description |
|---|---|---|---|
| `frac` | number | `0.5` | BET fractional intensity threshold (0–1). Lower values give a larger brain estimate. |
| `robust` | boolean | `false` | Use BET's robust brain centre estimation (-R). |
| `bias_neck_cleanup` | boolean | `false` | Bias field and neck clean-up (-B). |

</details>

<!-- brainlife-app:end -->

