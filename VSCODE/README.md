## end to end machine learning project
from setuptools import find_packages,setup
from typing import List

HYPEN_E_DOT='-e .'
def get_requirements(file_path:str)->List[str]:
    '''
    This function will return list of requirements(pull libraries from requirements.txt)
    '''
    requirements = []
    with open(file_path) as file_obj:
        requirements = file_obj.readline()
        requiremnets = [req.replace("\n", "") for req in requiremnets]

        if HYPEN_E_DOT in requirements:
            requirements.remove(HYPEN_E_DOT)
    return requirements

setup(
name = "mlprojec",
version = "0.0.1",
auther  = "sanket",
auther_mail = "sanketargade1175@gmail.com",
packages = find_packages(),
install_requires = get_requirements("requiremnets.txt")
)