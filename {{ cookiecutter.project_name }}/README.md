# {{cookiecutter.project_name}}

## Description
Project for client creation and management, featuring a compact storage system. Emphasis on data validation, logging, and testing is appreciated, alongside the project's organization and documentation.

## Development
To prevent dependency conflicts, installing a virtual environment via the `venv` library is advisable. Being a Python package, installation in development mode is required for console execution. Use the command pip install -e . to install the package in development mode, allowing it to be executed from the console using python `{{cookiecutter.project_name}}/main.py`.

## Rubric
- Utilize `TinyDB` to create a database for client storage.
- The `pydantic` package has been used for data validation.
- The `loguru` logging package has been used for log recording.
- The `pytest` package has been used for the creation of tests.
- A Docker image of the project should be generated using a `Dockerfile` where the entrypoint is the project's main script.
- For `pyarrow` dump, it is recommended to use a schema to avoid problems with data types.
- The project has a clear, modular structure and is well documented.


## Methods specifications
- Add client
    ```
    params:
        --name <string>
        --email <string>
        --age <int>
        --country <str>

    output:
        {
            "id": <int>,
            "name": <string>,
            "email": <string>,
            "age": <int>,
            "country": <str>
        }
    
    example:
        python {{cookiecutter.project_name}}/main.py add-client --name Peter --email peter@test.com --age 32 --country ES

    ```
- Get client
    ```
    params:
        --id <int>

    output:
        {
            "id": <int>,
            "name": <string>,
            "email": <string>,
            "age": <int>,
            "country": <str>
        }
    
    example:
        python {{cookiecutter.project_name}}/main.py get-client --id 1
    ```

- Dump clients
    ```
        output:
            .parquet file with all the clients, partitioned by country
        
        example:
            python {{cookiecutter.project_name}}/main.py dump
    ```