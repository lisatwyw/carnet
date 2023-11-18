
# DOS and UNIX commands

```
# Below works only in Linux OS
import subprocess
from ast import literal_eval

def run(command):
    process = subprocess.Popen(command, shell=True, stdout=subprocess.PIPE)
    out, err = process.communicate()
    print(out.decode('utf-8').strip())

print('# CPU')
run('cat /proc/cpuinfo | egrep -m 1 "^model name"')
run('cat /proc/cpuinfo | egrep -m 1 "^cpu MHz"')
run('cat /proc/cpuinfo | egrep -m 1 "^cpu cores"')

# CPU
print('# RAM')
run('cat /proc/meminfo | egrep "^MemTotal"')

# RAM
print('# OS')
run('uname -a')

# OS
print('# GPU')
run('lspci | grep VGA')
```
