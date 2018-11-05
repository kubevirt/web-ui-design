# VM List view

![List of VMs](img/1-1-main.png)

The VM list contains columns for the following:
- Name
- Namespace
- Status
  - running, off, failed, migrating, unknown
- Created
  - Date formatting should follow OpenShift's console, viewable [here](https://github.com/openshift/console/blob/master/frontend/public/components/utils/timestamp.jsx) and [here](https://github.com/openshift/console/blob/master/frontend/public/components/utils/datetime.ts)
  - If possible, the `div`'s title attribute should be set to the exact date/time of creation, including year
- Node
- IP Address
- FQDN

## Long list handling

For now, long lists of items will be displayed in an infinitely-scrollable list.

![Infinite scrolling](img/1-2-scroll.png)

## Filtering

### Item filters

![filters](img/2-1-filtering-items.png)

The predefined filters in the filter bar can be used to narrow the VM list by Status. The user clicks each tab to toggle it off/on.

If possible, `overflow-y: scroll` should be used to prevent the vertical scrollbar from disappearing when the list is shortened (preventing uncomfortable jumping).

### Title filter

![Title filter](img/2-2-filtering-title.png)

The title filter can also be used to further narrow down the VM list. Title filters do not override the filters set in the filtering bar, meaning hidden items will remain hidden even if searched for. This behavior could be a usability issue if users believe the title filter input to be a search input.

### Search filter (bonus)

![Searching by IP](img/2-3-filtering-search-ip.png)

If possible, the title filter could become a traditional search filter instead, allowing the user to filter results by any text string (or equivalent status) in any column. This could enable users to quickly find a VM by IP address, FQDN, or possibly other fields in the future. Multiple filters could be delineated by a comma in the search query. An information icon describing this advanced functionality would likely be necessary.

![Searching by status](img/2-4-filtering-search-status.png)

## Sorting

VM lists are sorted alphabetically by name by default. Clicking on a different column title will sort that column the same way. Clicking on the same column title twice will reverse the direction. This is all consistent with the OpenShift 4.0 direction.

![Sort by name](img/3-1-sort-name.png)

![Sort by age](img/3-2-sort-node.png)

![Sort by reverse age](img/3-3-sort-node-reverse.png)

## States and Actions

When a VM is OFF, the kebab on the right contains options to Run, Edit, or Delete that VM.

![VM selected while off](img/4-1-selected-vm-off.png)

When a VM is Running, the kebab menu contains options to Connect to Console (if available), Edit, Delete, Suspend, Reboot, Force Reboot, Shutdown, Force Shutdown, or Migrate the VM.

![VM selected while running](img/4-2-selected-vm-running.png)