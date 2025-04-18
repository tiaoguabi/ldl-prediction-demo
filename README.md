# ldl-prediction-demo
Online access URL:
https://tiaoguabi.github.io/ldl-prediction-demo/

# LDL-C Prediction Web Demo

This project provides an interactive web-based tool for estimating low-density lipoprotein cholesterol (LDL-C) using four different methods based on standard lipid panel inputs:

- ONNX Machine Learning Model (based on EBM)
- Friedewald Equation
- Martin/Hopkins Equation
- Sampson Equation

Users can input Total Cholesterol (TC), Triglycerides (TG), and HDL-C in mmol/L, and the application will automatically convert the values into mg/dL for calculation and display the results in both units.

---

## 🔬 Features

- Input in mmol/L, automatic conversion to mg/dL
- Real-time LDL-C prediction using a pre-trained ONNX model
- Side-by-side comparison of three widely-used LDL-C estimation formulas
- Results shown in both mg/dL and mmol/L
- Built-in warning for invalid or negative LDL-C values
- Fully client-side, no backend needed

---

## 📊 LDL-C Calculation Methods

### 1. Friedewald Equation
> `LDL-C = TC - HDL-C - TG / 5`  
Assumes TG < 400 mg/dL, uses a fixed TG:VLDL-C ratio.

Reference:  
Friedewald WT, Levy RI, Fredrickson DS. *Clin Chem* 1972;18:499-502.

---

### 2. Martin/Hopkins Equation
> `LDL-C = TC - HDL-C - (TG / adjustable_factor)`  
Uses an adjustable factor based on TG and non-HDL-C levels. This project strictly follows the original factor lookup table from the publication.

Reference:  
Martin SS, et al. *JAMA* 2013;310(19):2061–2068.

---

### 3. Sampson Equation
> A non-linear regression equation designed for use across TG ranges, including patients with hypertriglyceridemia.

Reference:  
Sampson M, et al. *JAMA Cardiol* 2020;5(5):540–548.

---

## 🧪 LDL-C Unit Conversions

To convert between mg/dL and mmol/L:

| Analyte            | mg/dL → mmol/L              | mmol/L → mg/dL              |
|--------------------|-----------------------------|-----------------------------|
| TC, LDL-C, HDL-C   | ÷ 38.67                     | × 38.67                     |
| Triglycerides      | ÷ 88.57                     | × 88.57                     |

---

## 🧠 ONNX Model

The ONNX model used here is trained using EBM (Explainable Boosting Machine) with Python, and exported via `skl2onnx`. It accepts inputs:

- `Total cholesterol` (mg/dL)
- `HDL cholesterol` (mg/dL)
- `triglycerides` (mg/dL)

---

## 🚀 How to Use

1. Open the HTML page in any modern browser.
2. Enter values for Total Cholesterol, Triglycerides, and HDL-C in mmol/L.
3. Click Predict LDL.
4. View predictions and formula-based estimates in the results table.

---

## ⚠️ Legal & Copyright Notice

- Friedewald and Sampson equations are in the public domain and can be freely implemented.
- The Martin/Hopkins equation is derived from a published method involving a proprietary factor table. This project uses the factor logic as published in the original academic article for educational and research purposes only.
- Please consult institutional IP policies before deploying this tool commercially.

---

## 📚 References

1. Friedewald WT, Levy RI, Fredrickson DS. *Clin Chem*. 1972;18:499-502.
2. Martin SS, Blaha MJ, Elshazly MB, et al. *JAMA*. 2013;310:2061–2068.
3. Sampson M, Ling C, Sun Q, et al. *JAMA Cardiol*. 2020;5(5):540–548. doi:10.1001/jamacardio.2020.0013

---

## 📄 License

This repository is released under the MIT License unless otherwise specified. Please review all dependencies and data sources used in your deployment context.

---

## 👨‍⚕️ Disclaimer

This tool is intended for educational and research use only. It is not a medical device and must not be used for diagnostic or treatment decisions. Always consult with licensed healthcare professionals.

