# VM Details

Clicking on the name of the Virtual Machine in the list view will take the user into the details view of that VM.

![List of VMs](img/UI-VM-list.jpg)


The details of the Virtual Machine are separated into tabs:
- Overview
- YAML
- Snapshots
- Networks
- Disks
- Consoles

On the overview tab both a general overview and utilization are provided.

![Virtual Machine Details](img/UI-VM-details.jpg)

Additional information is provided via tooltips for status and boot order.
![Virtual Machine Details](img/UI-VM-details-status-tooltip.jpg)

The user can then edit the overall details of the VM from the action menu in the top right.

![Virtual Machine Details](img/UI-VM-details-action-menu.jpg)

Once in Edit mode all available options will show as editable.

![Virtual Machine Details](img/UI-VM-details-edit-view.jpg)

In this mode the boot order can be arrange with drag and drop. A tooltip is provided to clarify this action.
![Virtual Machine Details](img/UI-VM-details-edit-boot-menu-tooltip.jpg)

In some scenarios, the edits a user makes to a VM will not be applied to it until the VM has been restarted.
![Virtual Machine save popup](img/UI-VM-details-save-popup.jpg)

Once the details have been edited the user can save their changes or cancel. Either action would send them back to the overview page.

When changes are saved the user is notified via an inline notification.

![Virtual Machine save](img/UI-VM-details-edit-saved-notification.jpg)
 