# Working with `pip`

!!! note
    This page is a work in process.

## Serializing Project Package Dependencies

```bash
pip freeze > requirements.txt
```



The pipreqs package can be used to create `requirements.txt` files with just the packages used in your local project.
```bash
python3 -m pip install pipreqs
```