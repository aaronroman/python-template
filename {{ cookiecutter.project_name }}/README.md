# {{cookiecutter.project_name}}

## Description
Small project for the creation of a client and its subsequent query. A small in-memory storage system has been created for managing clients. The use of data validation with pydantic, the use of logging, and the use of tests will be valued. As well as the project's structure and its documentation.

## Development
It is recommended to install a virtual environment using the venv library to avoid conflicts with project dependencies. As it is a Python package, it is necessary to install it in development mode to be able to execute it from the console. With the command pip install -e ., the package will be installed in development mode. It can be executed from the console with the command python {{cookiecutter.project_name}}/main.py.

## Rubric
- The pydantic package has been used for data validation.
- The logging package has been used for log recording.
- The pytest package has been used for the creation of tests.
- The project has a clear, modular structure and is well documented.
- A Docker image of the project should be generated using a Dockerfile where the entrypoint is the project's main script.

## Specifications
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
        python {{cookiecutter.project_name}}/main.py add-client --name Peter --email peter@test.com --age 32 --enable 1

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