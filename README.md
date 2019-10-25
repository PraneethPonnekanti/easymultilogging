..
## Package Description, Installation and usage guide.

```
Use cases : 
    To create logfiles and write to multiple log files from the same script.
    

    Create an object of the CreateLogs class in your script with the required arguments, use "object.logger.logging_level" as a wrapper around the process for which you wish to capture the logs.

```

#1. Install package

```
pip install easymultilogging
```

#2. Usage
```
#CreateLogs is the class inside easymultilogging package that is to be imported.
from easymultilogging import CreateLogs as cl
```

#3. Arguments for CreateLogs class
```
	CreateLogs class Arguments : 
        log_dest_dir = Path to the directory where the log file is to be saved. 
        log_file_name = Name of the log file. [The log file can be accessed at log_dest_dir/log_file_name]
        log_format = Can be defined while intiallizing the class object, however the default argument is '%(asctime)s %(name)-12s%(levelname)s:%(message)s'
        log_set_level = User - defined set levels. Default value = 'DEBUG'. For all other valid inputs, please refer "https://stackoverflow.com/questions/2031163/when-to-use-the-different-log-levels"
```

#3. Sample script

```
#CreateLogs is the class inside easymultilogging package that is to be imported.
from easymultilogging import CreateLogs as cl

#Create an object of the class CreateLogs. 
# Lets go ahead and create objects 'p1,'p2' for our sample script 

p1 = cl(log_dest_dir = 'C:\Opex Projects\McD-Toys-master\Source', log_file_name = 'testpackage_29.txt', log_set_level = 'DEBUG')
p1.logger.debug("-------process : 1")
         
p2 = cl(log_dest_dir = 'C:/Opex Projects/McD-Toys-master/', log_file_name = 'testpackage_30s.txt')
p2.logger.info("------process : 2")

#p2.logger.info(subprocess.check_output[arg1,arg2]) is a good example of how the object can be used to capture subprocess execution logs as well !
      
#cl('C:/Opex Projects/McD-Toys-master', 'testpackage_withoutKeywordInput.txt', '%(asctime)s %(name)-12s%(levelname)s:%(message)s', logging.INFO)

```