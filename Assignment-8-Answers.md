# Answers to Assignment 8 Part 3

Add your answers to the questions in Assignment 8 Part 3, Step 2 below. 

## Vulernability Remediation:
### Vulnerability 1: 
1. Which package or library are you addressing?
Package : pkg:pypi/pyyaml@5.1
2. Which CVE is linked to this vulnerability?
Vulnerability : CVE-2019-20477
PyYAML 5.1 through 5.1.2 has insufficient restrictions on the load and load_all functions because of a class deserialization issue, e.g., Popen is a class in the subprocess module. NOTE: this issue exists because of an incomplete fix for CVE-2017-18342.
3. What remediation steps do you suggest?
The steps in order to resolve this vulnerability are to:
- Upgrade the PyYAML package with "pip install --upgrade PyYAML"
- Then replace the yaml.load function with the yaml.safe_load which
restricts PyYAML's ability to read data types preventing code exicution.

### Vulnerability 2:
1. Which vulnerability are you addressing?
Package : pkg:pypi/pyyaml@5.1
2. Which CVE is linked to this vulnerability?
Vulnerability : CVE-2020-1747
A vulnerability was discovered in the PyYAML library in versions before 5.3.1, where it is susceptible to arbitrary code execution when it processes untrusted YAML files through the full_load method or with the FullLoader loader. Applications that use the library to process untrusted input may be vulnerable to this flaw. An attacker could use this flaw to execute arbitrary code on the system by abusing the python/object/new constructor.
3. What remediation steps do you suggest? 
The steps in order to resolve this vulnerability are to:
- Upgrade the PyYAML package with "pip install --upgrade PyYAML"
- Remove yaml.full_load and yaml.load as it allows decentralized code execution.