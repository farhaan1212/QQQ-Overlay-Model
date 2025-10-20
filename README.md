# QQQ-Overlay-Model
## Analysis Workflow & Key Findings

This Jupyter Notebook documents a comprehensive, iterative research process for developing and validating a quantitative risk overlay for QQQ, culminating in a final, robustness-enhanced strategy suitable for paper trading:

1.  ****Baseline Model:** Implemented an initial strategy using online machine learning and risk controls.
2.  **Initial Backtest:** Showed potentially optimistic results.
3.  **Rigorous Walk-Forward Test:** Applied a gated walk-forward protocol which revealed significant overfitting and OOS performance degradation for the raw baseline model.
4.  **Regime Diagnostics:** Analyzed the OOS failure, identifying specific market conditions where the core logic showed potential.
5.  **Rule Refinement & Validation:** Systematically tested, optimized, and performed strict OOS validation of filtered trading rules ('Rule A', 'Union') achieving strong *gross* OOS performance (Sharpe ~1.35).
6.  **Extensive Robustness Audit:** Subjected the refined 'Union' strategy to a battery of tests (Leakage, Sensitivity, DSR/PSR, Purged CV, Sub-period, Costs, Bootstrap, Concentration), confirming statistical significance after costs but initially flagging **concentration risk** and statistical uncertainty.
7.  **Concentration Mitigation & Final Optimization:** Implemented and optimized ("robustness-aware search") specific **dynamic position capping logic ('smart-cap')** explicitly designed to reduce the strategy's dependence on outlier trades identified in the audit.
8.  **Final Validated Strategy (`U_live` / `U(best-cap2)`):** The final selected strategy, incorporating robustness enhancements, demonstrated strong and validated OOS performance:
    * **Sharpe Ratio ≈ 1.34**
    * **Annualized Return ≈ 9.2%**
    * **Max Drawdown ≈ -12.2%**
    * **Improved Concentration:** Successfully reduced reliance on top trades.
    * **Passed Robustness Gauntlet:** Successfully passed final automated audit checks, including leakage, temporal stability (LOYO), **advanced bootstrap methods (e.g., Marcos Lopez de Prado's techniques)**, and transaction cost resilience (Net Sharpe > 0.8 @ 25bps).
9.  **Conclusion:** Through an iterative process focused on validation and robustness, the research successfully developed and rigorously validated a quantitative overlay strategy (`U_live`). It demonstrates a statistically significant, cost-resilient edge with mitigated concentration risk, passing final checks deeming it suitable for paper trading evaluation.
10. **Visualizations:** Includes plots comparing performance across the different stages of refinement and analysis.**
