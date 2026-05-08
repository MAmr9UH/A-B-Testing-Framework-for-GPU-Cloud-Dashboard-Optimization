# A/B Testing Framework for GPU Cloud Dashboard Optimization

## Project Overview

This project builds an A/B testing framework for a GPU cloud dashboard optimization use case. The goal is to evaluate whether a smart dashboard experience can improve GPU job completion outcomes compared to a standard dashboard.

The project uses real GPU workload and node capacity data, then creates a simulated A/B testing layer to demonstrate experiment design, statistical testing, and product analytics methodology.

## Business Problem

GPU cloud users may submit jobs without clear visibility into:

- GPU availability
- workload complexity
- job duration risk
- resource constraints
- configuration recommendations

This can lead to failed, abandoned, or inefficient jobs.

The business question is:

> Can a smarter GPU dashboard improve job completion rates by giving users better workload guidance?

## Experiment Design

Two dashboard variants were compared:

| Variant | Description |
|---|---|
| A | Standard GPU dashboard |
| B | Smart GPU dashboard with guidance, risk warnings, and configuration recommendations |

The primary success metric is:

> Job completion rate

## Dataset

The project uses two datasets:

| Dataset | Description |
|---|---|
| `job_info_df.csv` | Job-level GPU workload data |
| `node_info_df.csv` | Node-level GPU and CPU capacity data |

The job dataset includes information such as:

- GPU model
- CPU request
- GPU request
- worker count
- submit time
- duration
- job type

The node dataset provides infrastructure context, including GPU capacity and CPU capacity by node.

## Methodology

The analysis includes:

1. Dataset inspection
2. Infrastructure and workload overview
3. Duration feature engineering
4. Outlier handling using the 99th percentile
5. A/B group simulation
6. Job completion outcome simulation
7. Lift calculation
8. Two-proportion z-test
9. Confidence interval calculation
10. Results visualization
11. Business recommendation

## Key Results

Variant B outperformed Variant A.

| Metric | Value |
|---|---:|
| A Completion Rate | 69.44% |
| B Completion Rate | 73.29% |
| Absolute Lift | 3.86 percentage points |
| Relative Lift | 5.55% |
| P-value | 0.000000 |
| 95% Confidence Interval | 3.60% to 4.12% |

## Business Recommendation

The simulated A/B test shows that the smart GPU dashboard improves job completion outcomes compared to the standard dashboard.

Because Variant B achieved a higher completion rate, produced a statistically significant result, and showed a positive confidence interval for lift, Variant B would be recommended for rollout in this simulated experiment.

## Tools Used

- Python
- Pandas
- NumPy
- Statsmodels
- Plotly Express
- Jupyter Notebook

## Limitations

This project uses real GPU workload and node capacity data, but the A/B assignment and job completion outcome are simulated because the original dataset does not include live experiment labels or completion-success records.

The purpose of this project is to demonstrate experiment design, statistical testing, and product analytics methodology for GPU cloud dashboard optimization.

## Future Improvements

This framework could be extended with real production data, including:

- actual dashboard variant assignment
- real job completion logs
- queue time
- failure reasons
- user behavior data
- GPU utilization metrics
- dashboard interaction events

## Project Files

| File | Description |
|---|---|
| `AB.ipynb` | Main project notebook |
| `job_info_df.csv` | GPU job workload dataset |
| `node_info_df.csv` | GPU node capacity dataset |
