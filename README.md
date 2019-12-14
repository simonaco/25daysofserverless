# 25daysofserverless

1. In the Azure Portal:
Create a function app which you will use in the next steps
Under the associated storage account for the function create a container named `jokes`

1. Clone repo
```bash
git clone git@github.com:simonaco/25daysofserverless.git
cd 25daysofserverless
npx func azure functionapp publish <your-function-name> --python
```

1. Train the model that you will upload to the created storage container
```bash
python3.7 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt  # inside the 25daysofserverless folder
python create_model.py        # trains the model for that you will use for your API
```

1. Go to the storage section in the azure portal and upload the resulting `textgenrnn_weights.hdf5`

1. This should trigger the function to execute. If everything has worked then you should see no errors in the Live Metrics stream.
