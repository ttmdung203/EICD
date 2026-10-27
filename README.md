# EICD: Expense Item Category Dataset

EICD is a dataset of 11,077 personal expense items extracted from two
public receipt datasets (CORD and WildReceipt), annotated with a unified
12-category personal expense taxonomy. It supports research in expense
item classification and personal finance analytics.

This dataset accompanies the paper *"Toward AI-Driven Expense Analytics:
An Expense Item Classification Dataset"* (under review, 2026).

## Files

- `train.jsonl` — 8,235 records
- `validation.jsonl` — 220 records
- `test.jsonl` — 2,622 records
- `categories.json` — the 12 category definitions

Each line in the `.jsonl` files:
```json
{"item_name": "-TICKET CP", "receipt_index": 0, "source_dataset": "CORD", "category": "Transportation"}
```

| Field | Description |
|---|---|
| `item_name` | Textual description of the purchased item |
| `receipt_index` | Identifier of the original receipt in the source dataset |
| `source_dataset` | `CORD` or `WildReceipt` |
| `category` | One of the 12 categories in `categories.json` |

## Categories

Food and Beverage, Groceries, Transportation, Shopping, Entertainment,
Health/Wellness and Personal Care, Housing, Utilities, Education, Travel,
Financial, Other. See `categories.json` for full definitions.

## Annotation

Labels were produced via a human-in-the-loop process: DeBERTa-v3 zero-shot
suggestions, followed by manual annotation and a second review pass.
Quality was validated on an independent blind annotation of a stratified
500-sample subset, achieving Cohen's Kappa = 0.8444.

## Citation

```bibtex
@inproceedings{tran2026eiccd,
  title={Toward AI-Driven Expense Analytics: An Expense Item Category Dataset},
  author={Tran, Thi My Dung and Zhang, Zhongwei and Nguyen-Huy, Thong and Sahi, Aqeel},
  booktitle={[to be updated upon acceptance]},
  year={2026}
}
```


## Source Data and Licences

EICD is derived from the item names in two public receipt datasets:

- **CORD**: licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
- **WildReceipt**: licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)

We extracted item names from the original ground truth annotations and added expense category labels. No receipt images are included.
If you use EICD, please also cite the original CORD and WildReceipt papers.
