# bryckster
A simple Python CLI tool to convert notebooks from Jupyter to Databricks Notebooks format.

## Usage

* Clone locally:
```git clone https://github.com/rafaelvp-db/bryckster.git```

* Create a virtual environment and install requirements:
```bash
python -m venv .venv && source .venv/bin/activate && \
pip install --upgrade pip && pip install -r requirements.txt
```

* Open a terminal and run:
```bash
python bryckster.py run \
    --input_path JUPYTER_NOTEBOOKS_FOLDER \
    --output_path DATABRICKS_NOTEBOOKS_FOLDER
```

## Github Actions

* This repo has been setup in a way that it showcases the following example:
    * Jupyter notebooks are stored in the `jupyter` folder
    * A CICD pipeline looks into the `jupyter` folder and converts all of them into Databricks format, outputs them into the `databricks` folder
    * As a last step, input `.ipynb` files are removed
    * To give it a try, you can fork this repo and add `ipynb` files into the Jupyter folder. Once you commit, Github Actions will run the steps above.
## Other Tips & Tricks

* It is possible to import **Jupyter Notebooks** directly into a **Databricks Workspace** and have them converted automatically.
* However, when using Repos integration the conversion does not work out of the box.
* You can add `bryckster` as a step in your CICD pipeline, so that whenever someone pushes an `.ipynb` into your repo, it gets converted to the format expected by Databricks.
* Apart from `bryckster`, it is also possible to import Jupyter Notebooks directly into a Databricks workspace by using the [Workspace REST API](https://docs.databricks.com/dev-tools/api/latest/workspace.html#import) or the `databricks workspace` CLI.
* One common caveat with Jupyter Notebooks is that since they store the output, they can also get pretty big. With `bryckster` you can simply get rid of those (if needed) prior to pushing into a Git Repo, for cleanliness sake.

## Additional Reference

* [Git Integration with Databricks Repos](https://docs.databricks.com/repos/index.html)
* [Databricks Workspace CLI](https://docs.databricks.com/dev-tools/cli/workspace-cli.html)
