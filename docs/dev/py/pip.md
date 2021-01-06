# Working with `pip`

## Serializing Project Package Dependencies

[`pip`][3] doesn't have an automatic mechanism for serializing the different project dependencies you have.  Typically with a Python project, you would document your project's dependencies in a `requirements.txt` file.  This would allow you to quickly re-install all your dependencies when the project is moved to a new machine or re-build for a deployment.


### Default Option: `pip freeze`

You can use the [`freeze`][1] command, however, to output all of the dependencies you have installed and that output can then be sent to a `requirements.txt` file using the command below:

```bash
pip freeze > requirements.txt
```

Serialize all `pip` modules.
{: .caption }

### Better Option: `pipreqs`

The [`pipreqs`][2] package can be used to create `requirements.txt` files with just the packages used in your local project.  Since `pip freeze` saves all of the packages in your environment—including the ones you don't actually use in your project, `pipreqs` is a cleaner solution.

To install `pipreqs`:

```bash
pip install pipreqs
```

You can then generate your project's requirements using the global `pipreqs` command:

```bash
$ pipreqs /project/location
Successfully saved requirements file in /project/location/requirements.txt
```

[1]: https://pip.pypa.io/en/stable/reference/pip_freeze/
[2]: https://pypi.org/project/pipreqs/
[3]: https://pip.pypa.io/en/stable/