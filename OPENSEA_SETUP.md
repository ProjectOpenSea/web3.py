# Overview

We have altered this package to allow websockets v10 to get around some package dependency problems

# Build

```
python3 setup.py bdist_wheel
```

# Publish

Ensure twine is install

```
python3 -m pip install twine
```

Upload the bdist_wheel

```
twine upload --repository-url https://opensea-prod-718537141989.d.codeartifact.us-east-1.amazonaws.com/pypi/opensea-private/ -u aws -p $(aws --profile os-infra-admin codeartifact get-authorization-token --domain opensea-prod --domain-owner 718537141989 --query authorizationToken --output text) dist/web3-5.29.2.dev0-py3-none-any.whl
```