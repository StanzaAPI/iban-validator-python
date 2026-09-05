# Global IBAN, BIC/SWIFT & Bank Routing Validator API — Python SDK

[![PyPI version](https://img.shields.io/pypi/v/stanzaapi-iban-validator.svg)](https://pypi.org/project/stanzaapi-iban-validator/)
[![Python Versions](https://img.shields.io/pypi/pyversions/stanzaapi-iban-validator.svg)](https://pypi.org/project/stanzaapi-iban-validator/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stanza API](https://img.shields.io/badge/Powered%20by-Stanza-blue)](https://stanzaapi.com)

> ISO 13616 MOD-97 IBAN checksum verification, ISO 9362 BIC/SWIFT validation, and national bank routing extraction across 87 countries.

Official, zero-dependency Python 3.8+ client library for **Global IBAN, BIC/SWIFT & Bank Routing Validator API**, built on the [Stanza Micro-API Network](https://stanzaapi.com). Intended for enterprise data pipelines, backend verification, and sub-5ms edge compute.

* 🌐 **Live Web Playground:** [Test your inputs online](https://stanzaapi.com/tools/iban-validator)
* 📚 **API Documentation:** [View full schema on Stanza](https://stanzaapi.com/tools/iban-validator)
* ⚡ **Platform Overview:** [Explore the Stanza Developer Network](https://stanzaapi.com)

---

## 📦 Installation

```bash
pip install stanzaapi-iban-validator
```

---

## 🚀 Quickstart

```python
import os
from stanzaapi_iban_validator import IbanValidatorClient

# Initialize client (api_key optional for local evaluation)
client = IbanValidatorClient(
    api_key=os.getenv("STANZA_API_KEY")
)

# Execute deterministic validation
response = client.validate("DE89370400440532013000")

if response.get("success"):
    print("Verification Success:", response["data"])
else:
    print("Validation Error:", response.get("error"), response.get("code"))
```

---

## 📄 Example Response

```json
{
  "success": true,
  "data": {
    "valid": true,
    "iban": "DE89370400440532013000",
    "country_code": "DE",
    "bank_code": "37040044",
    "bic_candidate": "COBADEFFXXX"
  }
}
```

---

## ⚙️ Client Options

| Parameter | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `api_key` | `Optional[str]` | `os.getenv("STANZA_API_KEY")` | Your [Stanza API Key](https://stanzaapi.com). Required for production quotas. |
| `base_url` | `Optional[str]` | `"https://stanzaapi.com"` | API endpoint base URL. Custom endpoints supported for VPC enclaves. |
| `timeout` | `int` | `15` | Request timeout in seconds. |


---

## 🔗 Useful Links

* [Global IBAN, BIC/SWIFT & Bank Routing Validator API Interactive Sandbox](https://stanzaapi.com/tools/iban-validator)
* [Stanza Developer Directory](https://stanzaapi.com)
* [Source Code & Issue Tracker](https://github.com/stanzaapi/iban-validator-python)

## 📄 License

MIT © Stanza — Powered by [Stanza](https://stanzaapi.com).
