# VM List view

![List of VMs](img/1-0-main.png)

The VM list contains columns for the following:
- Name
- Namespace
- Status
  - Running, Off, Error (with custom messages), Warning, Cloning/Migrating, Unknown
- Created
  - Date formatting should follow OpenShift's console, viewable [here](https://github.com/openshift/console/blob/master/frontend/public/components/utils/timestamp.jsx) and [here](https://github.com/openshift/console/blob/master/frontend/public/components/utils/datetime.ts)
  - If possible, a tooltip should appear on hover with the exact creation date, including year.
- Node
- IP Address
- FQDN

## Errors and Warnings

![VM list errors and warnings](img/1-1-warning.png)

Hovering over an error or warning in a VM's status column should display a tooltip with a brief description of the issue. If multiple errors/warnings exist, the description should be more generic. Clicking on an error or warning should bring the user to the VM's Events page for more details.

## Filtering

### Item filters

![filters](img/2-0-filtering.png)

The predefined filters in the filter bar can be used to narrow the VM list by most statuses. The user clicks each filter to toggle it on and off.

If possible, `overflow-y: scroll` should be used to prevent the vertical scrollbar from disappearing when the list is shortened while filtering (preventing uncomfortable jumping).

### Name filter

![Name filter](img/2-1-filtering-name.png)

The name filter can also be used to further narrow down the VM list. Name filters do not override the filters set in the filtering bar, meaning hidden items will remain hidden even if searched for.

(Note: This behavior could be a usability issue if users expect the title filter input to behave like a traditional search input.)

### Search filter (concept)

![Searching by IP](img/2-2-filtering-search-ip.png)

If possible, the name filter could become a traditional search filter instead, allowing the user to filter results by any text string in any column. This could enable users to quickly find a VM by IP address, FQDN, or possibly other fields in the future. Multiple filters could be delineated by a comma in the search query. A help icon describing this advanced functionality would likely be necessary.

![Searching by status](img/2-3-filtering-search-status.png)

## Sorting

VM lists are sorted alphabetically by name by default. Clicking on a different column title will sort that column the same way. Clicking on the same column title twice will reverse the sort direction.

![Sort by name](img/3-0-sort-name.png)

![Sort by age](img/3-1-sort-node.png)

![Sort by reverse age](img/3-2-sort-node-reverse.png)

## States and Actions

When a VM is off, the actions kebab contains options to Run, Edit, Migrate, Clone, Create Template, Take Snapshot, and Delete the VM.

![VM actions while off](img/4-0-selected-vm-off.png)

When a VM is running the Run option is replaced with two dropdowns for Power and Connect to Console.

![VM actions while running](img/4-1-0-selected-vm-running-power.png)

The Power dropdown contains options to Suspend, Restart, or Shut down the VM. Because these are potentially destructive actions, clicking any of these options will display a modal for the user to confirm.

![Suspend VM modal](img/4-1-1a-power-modal-suspend.png)

The modals for Restart and Shut down include an additional button to "Force" the action. They also include warnings about the possibility for data loss.

![Restart VM modal](img/4-1-1b-power-modal-restart.png)

![Shut down VM modal](img/4-1-1c-power-modal-shut-down.png)

The Connect to Console dropdown contains quick links to the consoles that are enabled for the VM.

![Connect to consoles action](img/4-2-selected-vm-running-consoles.png)