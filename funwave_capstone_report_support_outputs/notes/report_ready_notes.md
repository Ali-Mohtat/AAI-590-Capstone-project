# Report-ready notes

## abstract_results

On the held-out test set, the physics-informed hybrid achieved the lowest mean RMSE (0.086), the lowest MAE (0.065), the highest correlation (0.891), and the lowest mean absolute timing error (0.231 s). Relative to the Stage 2 TCN, this corresponds to a 38.2% RMSE reduction and a 76.6% reduction in timing error. Relative to the deterministic physics baseline, the RMSE reduction was 79.6%.

## results_interpretation

The Stage 3 model outperformed the pure TCN on RMSE, MAE, correlation, timing error, and both spectral-band energy-error metrics, including a 34.8% reduction in infragravity-band relative error and a 58.1% reduction in sea-swell-band relative error. However, the mean sample-wise R² remained lower for Stage 3 (-1.969) than for Stage 2 (-1.399), which suggests that a smaller number of difficult edge cases still create large variance-normalized misses even though the overall waveform agreement is substantially better.

## stage2_training

The Stage 2 TCN was trained for 20 epochs, with the best validation loss (0.2362) reached at epoch 15. The training and validation curves both decreased over time, suggesting useful learning without catastrophic divergence.

## stage3_training

The Stage 3 hybrid was trained for 25 epochs, with the best validation loss (0.1137) reached at epoch 23. Its validation curve remained consistently below the early-epoch values and finished well below the Stage 2 best value, supporting the claim that the added physics-informed representation improved optimization and generalization.

## data_summary

The final modeling dataset contained 5,000 processed runs and 50,000 station-level samples. The median target-station depth was 4.76 m. The median sequence length was 1755 samples.

## depth_regime_note

Depth-wise evaluation shows that Stage 3 performs best in deeper stations, where RMSE fell to 0.062 and correlation rose to 0.961 for depths greater than 6 m. The shallowest stations (<=1 m) remained the hardest regime, with RMSE 0.106 and a strongly degraded R², making shallow-water edge cases the clearest target for future work.

