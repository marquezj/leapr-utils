# leapr-utils
Python scripts to generate and check LEAPR input files

Files contained in this directory:

- Directories:
* original_inputs/
  Original input files
 
* xml/
  Processed inputs in XML format
 
- Utility programs:
* leapr2xml.py
 Converts LEAPR inputs into XML files for internal usage.
Example:
  ./leapr2xml.py original_inputs/hh2o-endf6.njoy test.xml

* leapr_check.py
 Checks a LEAPR input in two steps: first it converts it to XML, then it checks for logical errors.
Example:
  ./leapr_check.py original_inputs/hh2o-endf6.njoy
 
* leapr_interpolator.py
 Interpolates a LEAPR model in XML format for a given temperature and produces a LEAPR input file.
 The program checks the original model and the interpolated model.
 ./leapr_interpolator.py xml/hh2o-endf6.xml test.leapr 301
 
* run_leapr.py
 Creates an interpolated LEAPR input file and runs it locally or in a remote server.
 
 The following variables need to be modified in the Python script:
 
 server: points to the server to run NJOY. A blank string means NJOY will run locally.
 tmpdir: points to the temporary directory in the server. "/tmp" is probably good.
 njoy_exec: points to the NJOY executable in the server.
 dryrun: if set to True, creates the input file but does not run it. Set it to False to actually run NJOY.

