# Readme for Copy-Fuse

## Usage Prequisites

<table>
    <thead>
	<tr>
	    <td>General Name</td>
	    <td>ArchLinux/CopyBoxLinux Package</td>
		<td>Raspbian</td>
	</tr>
    </thead>
    <tbody>
	<tr>
	    <td>Python 2</td>
	    <td>python2</td>
		<td>python2.7</td>
	</tr>
	<tr>
	    <td>Fuse</td>
	    <td>fuse</td>
		<td>fuse</td>
	</tr>
	<tr>
	    <td>Python Fuse Bindings</td>
	    <td>python2-fuse</td>
		<td>python-fuse</td>
	</tr>
	<tr>
	    <td>Python URLLib3</td>
	    <td>python2-urllib3</td>
		<td>python-urllib3</td>
	</tr>
	<tr>
	    <td>Python Setuptools utility</td>
	    <td>python2-distribute</td>
		<td>python-setuptools</td>
	</tr>
	<tr>
	    <td>Python YAML</td>
	    <td>python2-yaml</td>
		<td>python-yaml</td>
	</tr>
    </tbody>
</table>

## Usage How To

Clone the copy-fuse repo

	git clone https://github.com/copy-app/copy-fuse

'cd' to the copy-fuse repo

   	cd copy-fuse

ensure that copyfuse.py is executable

   	sudo chmod +x copyfuse.py

execute copyfuse.py

   	./copyfuse.py user@email.com password /path/to/mount/point

If you're on a shared machine where others can see the process list, you might not want to have them be able to see your username and password in teh process list.
For this, specify a configuration file with the -c parameter.

   	./copyfuse.py -c /etc/copyfuse.yaml

to unmount your Copy account

	fusermount -u /path/to/mount/point

## Example configuration file

	email:	user@email.com
	pass:	password
	mntdir:	/path/to/mount/point
	
## Troubleshooting

- SyntaxError: invalid token on line 228

  > The mount point given as the third argument to copyfuse.py does not exist, or is not a directory
