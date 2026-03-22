# Latchkey Runner Benchmarks

Performance benchmarks for [Latchkey](https://github.com/latchkey-dev) managed runners.

## What it measures

| Benchmark | Target | How |
|-----------|--------|-----|
| Startup latency | <10s warm, <90s cold | Time from job queued to first step |
| S3 cache throughput | >500 MiB/s | Save/restore 500MB payload via `actions/cache` |
| Docker layer cache | >5x speedup | Uncached vs cached build with ECR layer caching |

## Usage

1. Fork this repo (or copy the workflow into your own repo)
2. Make sure Latchkey managed runners are available for your org
3. Go to **Actions** > **Latchkey Runner Benchmark** > **Run workflow**
4. Select runner size and run
5. Check the job summary for results

## Requirements

- Latchkey GitHub App installed on your organization
- At least one runner size available (e.g. `latchkey-medium`)
- For Docker cache benchmarks: ECR cache must be configured

## Results

Results are displayed in the GitHub Actions **job summary** for each run. Each benchmark job produces a table with metrics and pass/fail against targets.
