# Deep Learning — From Scratch to Production (Course Repository Intro)

**Status:** Draft v0.1  
**Audience:** Upper-undergrad / early-grad / professional learners with Python & linear algebra background  
**Delivery:** Jupyter notebooks + short lectures + autograded labs  
**Hardware:** CPU is fine; GPU optional for a few stretch goals  

---

## Why this course?

This course bridges **math-first understanding** with **production-ready practice**.  
Learners implement neural networks from scratch (NumPy) to internalize forward/backward passes, then reproduce the same systems using modern frameworks (Keras/PyTorch), and finally connect the results to **business decisions** (e.g., profit-oriented thresholds in churn prediction).

---

## What makes it different

- **Dual-track pedagogy**: From-scratch math ↔ Framework best-practices  
- **Per-student personalization** (roll-number → unique hyperparameters & architectures) to reduce copy/paste and encourage original work  
- **Point-based autograders** that test shapes, derivatives, gradient checks, and learning signals  
- **Business framing**: precision/recall, ROC/PR, and profit-based threshold selection  

---

## Learning outcomes

By the end of the course, learners can:

- Derive and implement backpropagation for MLPs and CNNs.  
- Build, train, and evaluate models in Keras/PyTorch with clean, reproducible workflows.  
- Compare scratch vs. framework implementations and explain trade-offs.  
- Translate metrics into business actions (e.g., select a decision threshold that maximizes profit).  
- Produce clean reports, artifacts, and integrity stamps ready for review.  

---

## Prerequisites

- Python (≥3.9), NumPy, basic Pandas/Matplotlib  
- Calculus (chain rule), linear algebra, probability  
- Comfortable with Jupyter/Colab  

---

## Course structure (8 modules)

Each module includes a short video/reading and a hands-on lab.

1. **Foundations & Setup**  
   - Tensors, compute graphs, losses/metrics, reproducibility.

2. **MLP From Scratch I (Binary Classification)**  
   - Sigmoid/tanh/ReLU, BCE; forward pass; gradient intuition.  
   - *Lab:* `MLP_From_Scratch_Backprop_InstructionsOnly.ipynb`

3. **MLP From Scratch II (Full Backprop & Autograder)**  
   - Chain rule in code, training loop, gradient checks.  
   - *Lab:* Same notebook (part 2) + MLP point-based autograder  

4. **Regularization & Business Thresholds**  
   - Dropout/early stopping; precision/recall; ROC/PR; profit-based τ.  
   - *Lab:* Churn model variations (Keras), threshold sweep  

5. **CNN From Scratch (Vision)**  
   - Convolution, stride/pad, pooling, dense head, softmax CE; backward pass.  
   - *Lab:* `CNN_From_Scratch_InstructionsOnly.ipynb` (synthetic images)  

6. **Practical CNNs (Keras/PyTorch)**  
   - Augmentations, batchnorm, optimizers; reproducible training & evaluation.  
   - *Lab:* Framework CNN + comparison vs. scratch  

7. **Experimentation & Autograding**  
   - Hyperparameter sweeps, ablations, integrity artifacts; per-student configs.  
   - *Lab:* Roll-number personalized Keras vs. Scratch comparison  

8. **Capstone**  
   - Choose tabular churn uplift or small vision problem; deliver memo + notebook + artifact.  

---

## Repository layout
``
├── README.md                        
├── requirements.txt                   # Python deps (CPU-friendly)
├── env/                               # environment & launcher helpers
│   └── setup.sh
├── modules/
│   ├── 01-foundations/
│   │   ├── readings.md
│   │   └── quickstart.ipynb
│   ├── 02-mlp-scratch-i/
│   │   ├── MLP_From_Scratch_Backprop_InstructionsOnly.ipynb
│   │   ├── MLP_Backprop_Formulas.md
│   │   └── MLP_From_Scratch_Autograder_Graded.ipynb
│   ├── 03-mlp-scratch-ii/
│   │   ├── MLP_From_Scratch_Backprop_InstructionsOnly_RollCompare.ipynb
│   │   └── MLP_From_Scratch_Autograder_Graded.py
│   ├── 04-regularization-thresholds/
│   │   └── Churn_Model_Variations_InstructionsOnly.ipynb
│   ├── 05-cnn-scratch/
│   │   └── CNN_From_Scratch_InstructionsOnly.ipynb
│   ├── 06-cnn-framework/
│   │   └── CNN_Framework_Comparison.ipynb   # scaffold, students complete
│   ├── 07-experimentation/
│   │   └── Roll_Config_and_Integrity_Stamp.md
│   └── 08-capstone/
│       └── Capstone_Guide.md
├── autograders/
│   ├── mlp/
│   │   ├── MLP_From_Scratch_Autograder_Cell.py
│   │   └── MLP_From_Scratch_Autograder_Graded.ipynb
│   └── cnn/
│       └── CNN_Autograder_Graded.ipynb      # (to be added; mirrors MLP style)
├── solutions/ (private; instructors only)
│   ├── MLP_From_Scratch_Backprop_SOLUTIONS.ipynb
│   └── (CNN solutions, etc.)
├── data/
│   └── synthetic_generators.py              # reproducible tabular/vision data
├── scripts/
│   └── package_artifacts.py                 # bundles submission artifacts
└── assets/
    ├── branding/                            # slide templates, logos
    └── figures/
``

## Assessment & grading

**Lab grading (typical):**

- **From-scratch MLP (Modules 2–3) — 20 pts**  
  - Forward pass sanity (2), activation derivatives (3)  
  - BCE loss & clipping (2)  
  - Backprop gradient checks (6)  
  - Learning signal & tiny-run accuracy (4)  
  - Presentation/clarity (3)  

- **Churn thresholding (Module 4) — 20 pts**  
  - Correct metrics, profit model, τ selection, rationale, memo  

- **CNN from scratch (Module 5) — 20 pts**  
  - Conv/Pool fwd & bwd, gradient routes, softmax CE grad, learning signal  

- **Framework CNN (Module 6) — 20 pts**  
  - Clean model spec, training, evaluation, and comparison vs scratch  

- **Capstone (Module 8) — 20 pts**  
  - Problem framing, experiments, results, memo, artifact, reproducibility  

Rubrics are encoded inside autograders where feasible; presentation points may require manual review.

---

## Per-student personalization (roll-number)

To discourage copy/paste and guarantee unique work, certain labs derive a student-specific configuration from **ROLL_NUMBER**.

- **What changes per student:** hidden units, number of layers, activations, optimizer, learning rate, batch size, epochs, and random seed.  
- **Where it applies:** `MLP_From_Scratch_Backprop_InstructionsOnly_RollCompare.ipynb` and framework comparison labs.  
- **Enforcement:** Autograder verifies the submitted model matches the derived spec before awarding points.  

**Student instructions:**
1. Locate the cell labeled **“Student Identifier (Run First)”**.  
2. Set `ROLL_NUMBER` exactly as assigned.  
3. Run the cell to print your unique configuration.  
4. Use those values in both the from-scratch and framework implementations.  

---

## Integrity artifacts

Each graded notebook writes a small JSON file (e.g., `submission_<roll_clean>.json`) containing:

- roll_number, short hash, derived config (for audit)  
- Key metrics and timestamps  

These artifacts help instructors validate work at scale and streamline re-grading.

---

## Built-in vs. From-scratch comparisons

Several labs ask students to:

- Implement the model from scratch (NumPy) and with a framework (Keras/PyTorch).  
- Keep the same data splits and report Accuracy, Precision, Recall, ROC-AUC, PR-AUC.  
- Discuss trade-offs: development speed, stability, overfitting behavior, and deployment readiness.  

---

## Submission guidelines

- Export your notebook with outputs (save/commit the `.ipynb` after running all cells).  
- Include the integrity JSON artifact.  
- Where rubrics exist in autograders, leave the printed score visible at the bottom.  
- If using Colab, download the notebook to include in your submission.  

---

## Collaboration & academic honesty

- You may discuss concepts, but **code must be your own**.  
- Cite any external snippets you adapt (brief comment and link).  
- Roll-number configs mean your exact architecture and hyperparameters will differ from your peers.  

---

## Style & reproducibility

- Set and print your random seed where requested.  
- Keep functions pure where reasonable; modularize code (forward/backward per layer).  
- Use plots sparingly and label axes.  

---

## Roadmap (instructor-facing)

- Add `CNN_Autograder_Graded.ipynb` mirroring MLP checker  
- Add PyTorch track for Modules 6–8  
- Add lightweight nbconvert CI to ensure notebooks execute cleanly  
- Package dockerized environment for workshops  

---

## License

- **Code:** MIT (recommended)  
- **Content (text, figures, slides):** CC BY-NC-SA 4.0 (recommended)  
- Adjust to your institution’s policy.  

---

## Support & contact

- Open an issue for bugs or unclear instructions.  
- For grading concerns, contact the instructor/TA with your roll number, module, and attach the integrity artifact.  

---

## FAQ (quick)

- **Do I need a GPU?** No — CPU is sufficient for all core labs; GPU helps for stretch goals.  
- **Can I use PyTorch instead of Keras?** Where a framework is required, we recommend Keras first; a PyTorch variant may be provided in Module 6+.  
- **Will my config differ from classmates’?** Yes; that’s intended. Your autograder will check it.  

