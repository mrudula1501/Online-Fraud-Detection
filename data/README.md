# Create data folder
mkdir -p data

cat > data/README.md << 'EOF'
# Dataset Setup

## Option 1: Download via Kaggle API (Recommended)

### Prerequisites
1. Install Kaggle CLI:
```bash
pip install kaggle
```

2. Get API credentials:
   - Go to https://www.kaggle.com/settings/account
   - Click "Create New API Token"
   - Save the `kaggle.json` file to `~/.kaggle/`

### Download
```bash
kaggle datasets download -d jainilcoder/online-payment-fraud-detection
unzip online-payment-fraud-detection.zip -d data/
```

## Option 2: Manual Download

1. Visit: https://www.kaggle.com/datasets/jainilcoder/online-payment-fraud-detection
2. Click "Download"
3. Extract CSV file to `data/` folder

## Expected File Structure
```
Online-Fraud-Detection/
└── data/
    └── onlinefraud.csv  (6.3M+ records, ~550MB)
```

## Load in Python
```python
import pandas as pd

df = pd.read_csv('data/onlinefraud.csv')
print(df.shape)  # Should show (6362620, 10)
print(df.head())
```

## Dataset Columns

- **step**: Time step of the transaction (1-743)
- **type**: Type of transaction (PAYMENT, TRANSFER, CASH_OUT, DEBIT, CHECK)
- **amount**: Amount of the transaction
- **nameOrig**: Name of the originator (removed in analysis)
- **oldbalanceOrg**: Initial balance of originator
- **newbalanceOrig**: New balance of originator
- **nameDest**: Name of the destination (removed in analysis)
- **oldbalanceDest**: Initial balance of recipient
- **newbalanceDest**: New balance of recipient
- **isFraud**: Whether transaction is fraudulent (0 or 1)

EOF
