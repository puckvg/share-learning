# Task1 

## Aims 
- Understand basic module structure for a toy module that behaves as a calculator 
- Write unit tests for this module 
- Use pytest to run these tests 
- Use continuous integration (CI) to automatically run these tests on push 

Reference : https://github.com/puckvg/ActionsCalculatorLibrary but we can do better than this 

## Specifics
1. Open a file with an appropriate name (eg calculator.py) which has the following basic operations 
- add 
- subtract 
- multiply
- divide

2. Feel free to add any other basic functions you think a calculator should include 

3. Now write a test for every function you have defined above. Your test structure should look like: 
```
class Test[filename]:
    def test[function]:
        ....

    ...
```

4. Your module should now look like : 
```
parent module 
- calculator submodule 
    - __init__.py
    - calculator.py
- test submodule
    - imports calculator.py
```

4. Now install `pytest`. Run your tests with: 
```
python -m pytest -vrs tests
```
from the parent module 

5. You can also clean up any formatting using the following tools: 
```
isort, flake8, black
```

first checking the formatting with something like: 
```
python isort --check-only files.py
python flake8 --count files.py --statistics
python black --check files.py
```

then correcting the formatting with: 
```
python isort files.py
python autoflake --in-place --remove-unused-variables files.py
python black files.py
```

6. Ideally you want to run your unit tests and correct the formatting before every push to github. You can do this using github actions. 
- We need to tell github actions that we want to run certain commands before push, and which commands to run 
- We do this in a .yml file in .github/workflows/name.yml 
- See example here https://github.com/puckvg/ActionsCalculatorLibrary/blob/master/.github/workflows/test.yml but again we can do better 

- Test that everything passes on push 

7. Final cleanup to git repo 
- We should also have a .gitignore and a requirements.txt 
- gitignore usually includes eg pycache, but maybe also other stuff 
- requirements.txt tells the user downloading this repo exactly what packages they need (and only these)
- for this reason it's good practice to have different virtual envs and to install with the same package manager (eg pip, pip freeze)
