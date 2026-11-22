# Results: 204 Silent Data Corruption (SDC)

**Main goal:** Analyze ECC memory integrity via a CUDA fixed-pattern verifier  
**Tools:** Compile src/ecc_walk.cu with nvcc; run bin/ecc_walk; query nvidia-smi -q -d ECC

Reference results from the validation run on the system shown in each section (recorded 2026-11-22). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 80GB HBM3 (81559 MiB) · Intel(R) Xeon(R) Platinum 8470 · Ubuntu 24.04.5 LTS · kernel 6.8.0-149-generic · driver 595.112.07
- **Run:** 2026-11-22T14:02:42Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 01:22 · benchmark 00:21 · whole run 01:48
- **Source:** run 204_20261122_140242
- **Command:** `bash run_benchmark.sh --smoke --device-id 0 --memory-size 1 --pattern-type walking-1s --num-iterations 2 --duration 20000`

| # | Metric | Result |
|---|---|---|
| 1 | Uncorrected ECC errors (uncorrected_ecc_errors_count) | 0.0 |
| 2 | Corrected ECC errors (corrected_ecc_errors_count) | 0.0 |
| 3 | Wall-clock time, s (test_wall_clock_completion_time_s) | 20.555256366729736 |
| 4 | Device buffer size, GiB (device_buffer_gib) | 1.0 |
| 5 | Fixed-pattern fill/verify pass rate (fixed_pattern_fill_verify_pass_rate) | 100.0 |
<!-- /profile:smoke -->
