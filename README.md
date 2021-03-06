## Ansible Yaml2INI
## Description
Write an INI file given a provided YAML dictionary.

## Usage
Provide the following variables for this role to operate correctly.
`YAML2INI_DATA` will contain all of the data to be written to the INI file.
`YAML2INI_QUOTE_VALUES` will encapsulate the value of all options in a double quote.
`YAML2INI_OPTIONS` sets configuration options for the `community.general.ini_file` module. Pay special attention to the notes below.
```
---
YAML2INI_DATA:
  Section1:
    Option1: Value1
    Option2: 
      - "Use array notation when an option can be used multiple times"
      - "This would be another value for this option"
  Section2:
    Option3: Value2
    Option4: 
      - "Use array notation when an option can be used multiple times"
      - "This would be another value for this option"

YAML2INI_QUOTE_VALUES: yes # Default no; put double quotes around all values option="value"

# https://docs.ansible.com/ansible/latest/collections/community/general/ini_file_module.html
YAML2INI_OPTIONS: # Key=Value pairs for all community.general.ini_file parameters as of community.general collection (version 4.2.0)
  path: # This is the only parameter that is required
  section: # This parameter will be ignored as is defined as part of YAML2INI_DATA
  option: # This parameter will be ignored as is defined as part of YAML2INI_DATA
  value: # This parameter will be ignored as is defined as part of YAML2INI_DATA
```

## Support
For support, please raise an issue and provide the following items
- Sample task/playbook to replicate your issue
- Resultant file that is created.
- If modifying an existing file, please provide the unmodified version as well.
