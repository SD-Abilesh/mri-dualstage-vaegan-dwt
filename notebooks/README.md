# Notebook guide

The notebook collection records the main workflow, individual synthetic-noise experiments, and architectural ablations. The repetition is intentional: each experiment adapts the shared denoising pipeline to a different corruption or model variant.

## Main experiments

| Notebook | Purpose | Stored final output |
|---|---|---|
| [`all_noise_combined_dualstage_vaegan_dwt.ipynb`](main/all_noise_combined_dualstage_vaegan_dwt.ipynb) | Principal combined-noise Dual-Stage VAE-GAN-DWT workflow | 31.32 dB PSNR, 0.9168 SSIM |
| [`all_noise_combined_alternative.ipynb`](main/all_noise_combined_alternative.ipynb) | Alternative combined/vendor-aware workflow retained from development | 33.50 dB PSNR, 0.9423 SSIM |

The project report presents 33.50 dB PSNR and 0.9423 SSIM for the combined/vendor-aware experiment. These two notebooks are related development versions and should not be treated as identical runs.

## Individual-noise experiments

| Notebook | Corruption studied | Stored final output |
|---|---|---|
| [`gaussian_noise.ipynb`](individual-noise/gaussian_noise.ipynb) | Gaussian noise | 35.73 dB, 0.9456 SSIM |
| [`multiplicative_noise.ipynb`](individual-noise/multiplicative_noise.ipynb) | Multiplicative noise | 30.57 dB, 0.9755 SSIM |
| [`periodic_noise.ipynb`](individual-noise/periodic_noise.ipynb) | Periodic noise | 35.74 dB, 0.9895 SSIM |
| [`poisson_noise.ipynb`](individual-noise/poisson_noise.ipynb) | Poisson noise | 33.50 dB, 0.9658 SSIM |
| [`rician_noise_sigma_003.ipynb`](individual-noise/rician_noise_sigma_003.ipynb) | Rician noise, sigma 0.03 | 37.52 dB, 0.9624 SSIM |
| [`rician_noise_sigma_005.ipynb`](individual-noise/rician_noise_sigma_005.ipynb) | Rician noise, sigma 0.05 | 35.05 dB, 0.9403 SSIM |
| [`rician_noise_sigma_007.py`](individual-noise/rician_noise_sigma_007.py) | Rician noise, sigma 0.07 | Python source; no embedded output |
| [`speckle_noise.ipynb`](individual-noise/speckle_noise.ipynb) | Speckle noise | 31.57 dB, 0.9483 SSIM |
| [`vendor_specific_noise.ipynb`](individual-noise/vendor_specific_noise.ipynb) | Vendor-style corruption | No embedded final output |

## Ablations

| Notebook | Purpose | Stored final output |
|---|---|---|
| [`no_vae.ipynb`](ablations/no_vae.ipynb) | Removes the variational component | 36.95 dB, 0.9565 SSIM |
| [`no_dwt.ipynb`](ablations/no_dwt.ipynb) | Removes the wavelet component | 37.46 dB, 0.9618 SSIM |
| [`architectural_comparison.ipynb`](ablations/architectural_comparison.ipynb) | Loads saved experiment results for comparison | No embedded final output |

## Reading the saved results

The values above are transcribed from the notebooks' stored outputs. Several notebooks reuse the same directory for training and validation, so these values are historical development results rather than independently verified held-out estimates. They also do not always use exactly the same corruption settings or implementation version, which means comparisons across notebooks should be interpreted cautiously.

The notebooks preserve their original Colab cells, hard-coded Google Drive paths, and saved outputs. File names and folder organisation were cleaned for GitHub presentation; the training code itself was not silently rewritten.
