# vagrantTips
```
IDsVMs=($(VBoxManage list vms | awk -F '[{}]' '{print $2}'))

for idvm in "${IDsVMs[@]}";
do 
	echo "Powering off VM: ${idvm}..."
	VBoxManage controlvm "${idvm}" poweroff

	echo "Deleting VM ${idvm}..."
	VBoxManage unregistervm ${idvm} --delete
done
```
