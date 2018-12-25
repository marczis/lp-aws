# lp-aws

This is a bash "helper" to save and restore your AWS CLI configuration files from/to Last Pass

## How to use
All you need to do is to "source" the lp-aws file in bash

```bash
source lp-aws
```

or 

```bash
. lp-aws
```

You can do this ofcourse in your .bashrc if you like.

After doing so you will have two new function / "commands":
 - lp_aws_save
 - lp_aws_load

 ## lp_aws_save explained
 This function will parse your AWS Config and Credentials files, convert them into a json object, and add it into your Last Pass
 I used the "edit" function of lpass (Last Pass cli), so likely when ever you run save it will generate a new edit of the given
 aws profile. All profiles stored separatedly, under the aws_profiles "directory" in Last Pass. 

 ## lp_aws_load explained
 This function will iteratet over the saved profiles, parse the json objects from Last Pass into the credentials and config files.
 
 ## Notes
  - Both functions will save and load all the keywords from the original config files, so "supports" mfa_code and all other funky keywords
  - Both functions will overwrite existing profiles with the same names, so pick carefully

## Requiremenets
 - Last Pass cli - lpass
 - jq
 - crudini

 