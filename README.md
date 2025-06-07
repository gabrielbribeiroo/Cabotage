# 🧠 AHP Aggregation from Rating Matrix

This project implements the **Analytic Hierarchy Process (AHP)** using a matrix of ratings from multiple respondents. It converts individual evaluations into pairwise comparison matrices (PCMs), aggregates them via geometric mean, and calculates final criteria weights with consistency checks.

---

## 📌 Overview

- 📥 **Input**: Numeric ratings from respondents (e.g., 1–5 scale).
- 🔁 **Transformation**: Ratings → Pairwise Comparisons using Saaty scale.
- 🔬 **Aggregation**: Uses geometric mean to aggregate PCMs.
- 📊 **Output**:
  - Priority vector (final weights for each criterion).
  - Consistency Ratio (CR) to verify logical consistency.

---

## 📂 Project Structure

```plaintext
.
├── ahp_analysis.py       # Main script with all processing steps
├── README.md             # Project documentation
├── requirements.txt      # Required Python libraries (optional)
```

---

## 🚀 How to Run

1. **Clone the repository**:

```bash
git clone https://github.com/your-username/ahp-rating-analysis.git
cd ahp-rating-analysis
```

2. **Install dependencies** (optional step):

```bash
pip install -r requirements.txt
```

3. **Run the analysis**:

```bash
python ahp_analysis.py
```

---

## 🧮 Example Evaluation Matrix

The input matrix is defined as:

```python
evaluations = np.array([
    [5, 5, 5, 5, 3, 5, 3, 5, 5, 5, 5, 3],
    [5, 5, 5, 5, 5, 5, 5, 5, 5, 4, 5, 5],
    ...
])
```

Each row is a respondent, and each column corresponds to a **criterion**. The list of criteria is:

```python
CRITERIA_NAMES = [
    "Reduces Congestion",
    "Efficiency of Land Transport",
    "Mitigates Accident Risk",
    "Reduces Road Wear",
    ...
]
```

---

## 📈 Output Interpretation

- **Weights**: Relative importance of each criterion (as a percentage).
- **Consistency Ratio (CR)**:
  - ✅ CR < 0.10 → Acceptable
  - ⚠️ CR 0.10–0.20 → Marginally acceptable
  - ❌ CR ≥ 0.20 → Low consistency (suggest revision)

---

## 🧰 Methods Used

- **Saaty's AHP**: Converts rating differences to comparative judgments.
- **Geometric Mean Method**: Aggregates individual PCMs into a consensus matrix.
- **Eigenvalue Method**: Derives the final priority vector.
- **Consistency Index (CI)** and **Random Index (RI)**: Used to compute CR.

---

## 📊 Sample Output

```plaintext
--- Final Criteria Weights (Priority Vector) ---
Reduces CO2 Emissions            14.32%
Efficiency of Land Transport     12.10%
Reduces Cargo Theft              10.28%
...
```

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 👨‍💻 Author

- **Gabriel Ribeiro** – [@gabrielbribeiroo](https://github.com/gabrielbribeiroo)
- Email: gabrielbroliveira@gmail.com

---

## 🧠 References

- Saaty, T.L. (1980). *The Analytic Hierarchy Process*. McGraw-Hill.
- Forman, E.H., & Gass, S.I. (2001). *The Analytic Hierarchy Process—An Exposition*.

---