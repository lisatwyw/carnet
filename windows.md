
# DOS and UNIX commands

| Action	| DOS |	UNIX | |
| :-- | :-- | :--  | |
| change directory	| cd	| cd|
change file protection	attrib	chmod
compare files	comp	diff
copy file	copy	cp
delete directory	rd	rmdir
directory list	dir	ls
edit a file	edit	pico
environment	set	printenv
find string in file	find	grep
help	help	man
make directory	md	mkdir
move file	move	mv
rename file	ren	mv
show date and time	date, time	date
show disk space	chkdsk	df
show file	type	cat
show file by screens type filename	more	more
sort data	sort	sort

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
