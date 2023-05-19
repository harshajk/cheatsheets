# Conda virtual environment setup

    conda create --name <envname> python=<version> <optional dependencies>
    conda remove --name <envname> --all 
    
In an [activated environment][5], install packages via `conda` or `pip`:

    (envname)> conda install <package>
    (envname)> pip install <package>

[5]: https://conda.io/docs/user-guide/tasks/manage-environments.html#activating-an-environment
