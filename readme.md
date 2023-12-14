# About
This repository tests the applicability of DIF method to real-world images. Specifically, compressed or modified using trivial tools. If you are interested in DIF method please go to original repository.
# Experiments
The following modifications were tested:
* Resizing
* Rotation
* JPEG compression
* Contrast enhancement 
* One pixel shift

The pretrained fingerprints were used, that are provided by the authors. Bear in mind that the experiments were conducted only on 20 images in this repository.
# Results
Due to small size of the test set, the results are formulated as follows:
* PASS: No significant change in quality was observed
* FAIL: After applied modification the total accuracy dropped to ~50% 
* ?: Accuracy decreased, but not enough to consider it as FAIL

| Model      | Resizing | Rotation | JPEG compression | Contrast enhancement | One pixel shift |
|------------|----------|----------|------------------|----------------------|-----------------|
| dalle_2    | PASS     | PASS     | FAIL             | PASS                 | PASS            |
| dalle_mini | FAIL     | FAIL     | FAIL             | PASS                 | FAIL            |
| glide      | FAIL     | FAIL     | FAIL             | PASS                 | ?               |
| mj         | FAIL     | FAIL     | FAIL             | PASS                 | FAIL            |
| sd14       | FAIL     | FAIL     | FAIL             | PASS                 | FAIL            |
| sd21       | FAIL     | FAIL     | FAIL             | PASS                 | FAIL            |

Important to note that DIF for every failed experiment predicted "fake" for practically every modified image.

# Conclusion

DIF is not robust to any modifications that structurally change image content, which limits its applicability to real-world data. 

Moreover, modified images seem to be strongly correlated with fingerprints. This behaviour seems to be very unexpected and raises the questions on the structure of a fingerprint.
