Steps:

# clone the repository containing the code into the vm environment
- name: Check Code
      uses: actions/checkout@v6


# install the python to run the python code
  - name: Setup Python
      uses: actions/setup-python@v6
      with:
        python-version: "3.10"


# gets the required dependencies so that it can run tests
  - name: Install Dependencies
      run: pip install -r requirements.txt


# Checks the code if it pass or fails. If any of the test fails, the workflow fails immediately
   - name: Test
      run: pytest


  - name: Deployment
      run: echo "Deploying..."; echo "done."
