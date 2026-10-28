# PReSto BayGMST run on PReSto2k 0_1_0

This repository runs the PReSto BayGMST reconstruction on the [PReSto2k 0_1_0](https://lipdverse.org/PReSto2k/0_1_0/) compilation, screened against local HadCRUT5 temperature (presto-recipes [`PReSto2k_0_1_0_localfdr10`](https://github.com/paleopresto/presto-recipes/blob/pools-2026-10-27-r1/pools/config/PReSto2k_0_1_0_localfdr10.yml): temperature-interpreted records with a local correlation of the expected sign, BH FDR < 0.10 over 1850-2000, lag-1 autocorrelation at most 0.98): 236 records.

- Membership comes only from the published compilation, read from the
  LiPDverse whole-database export
  [2026-10-27](https://lipdverse.org/dev/export/database-2026-10-27/)
  (`compilations` table) by presto-recipes `pools/compilation_pool.R`.
- `query_params.json` (`mode: bundle`) pins the bundle by URL and sha256:
  presto-recipes release
  [pools-2026-10-27-r1](https://github.com/paleopresto/presto-recipes/releases/tag/pools-2026-10-27-r1).
  Its files are the compilation's LiPD files, checked against the export's
  md5 values and trimmed to the member records.
- The code and algorithm config are those of
  [presto-BayGMST-run-presto2k-0_0_1](https://github.com/paleopresto/presto-BayGMST-run-presto2k-0_0_1)
  at b4bb48c, unchanged, so this run differs from that one only in its data:
  PReSto2k 0_1_0 instead of 0_0_1. The records added and removed are listed in
  [changes_from_0_0_1.csv](https://github.com/paleopresto/presto-recipes/blob/pools-2026-10-27-r1/pools/compilations/PReSto2k/0_1_0/changes_from_0_0_1.csv).

Committing `query_params.json` triggers the reconstruction workflow.
