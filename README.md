# DEploid-Data-Benchmark-in_silico_lab_mixed_4s

This repository contains *in silico* mixture of 3D7, DD2, HB3 and 7G8, with
different mixing proportions.

|                     |3D7|DD2|HB3|7G8|
|---------------------|--:|--:|--:|--:|
|cb_3D7_HB3_DD2_7G8_w1|.1 |.2 |.3 |.4 |
|cb_3D7_HB3_DD2_7G8_w2|.25|.25|.25|.25|
|cb_3D7_HB3_DD2_7G8_w3|.2 |.2 |.2 |.4 |
|cb_3D7_HB3_DD2_7G8_w4|.3 |.3 |.3 |.1 |

The script extract VCF columns from `wg_vcf/GB4.wg.vcf.gz`, and overlap with
lab mixture panels to get the wanted SNP positions. We use `HB3.eg.vcf.gz` to
provide a total coverage profile, and draw binomial random variables
(alternative allele count) from the total coverage, with given probabilities
(WSAF, adjusted by error 0.01 to mimic sequencing error).

To generate the data:

```bash
R CMD BATCH generateLabMixedOf4s.r
```
