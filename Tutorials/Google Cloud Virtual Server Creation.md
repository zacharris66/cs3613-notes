We are going to use Google Cloud as our cloud hosting provider of choice for a couple of reasons. In order to use Google Cloud for our needs we have to first spin up an instance of a virtual machine.
## Account Creation
1. Visit Google Cloud: [cloud.google.com](http://cloud.google.com/)
2. Login with a Google Account
3. Accept Trial and add Billing Instructions
## Enable Compute Engine
1. Visit Google Cloud Console: [console.cloud.google.com](https://console.cloud.google.com)
2. Search for Compute Engine and select it from the search bar at the top of the page.
3. Enable Compute Engine API by clicking the Enable button.
	1. Wait for the enabling to finish, this may take several moments.
## Create Virtual Machine
1. Click on the Navigation Menu in the top left of the page and select Compute Engine.
2. Once the page loads, select the `Create Instance` button.
3. We will now select appropriate options, make sure to follow the notes below in order to avoid incurring charges.

| Configuration Category | Setting Name        | Value                                                                                             |
| ---------------------- | ------------------- | ------------------------------------------------------------------------------------------------- |
| Machine Configuration  | Name                | Name your machine with something descriptive. We will be using `astate-webdev` for this tutorial. |
|                        |                     | General Purpose selected.                                                                         |
|                        | Series              | E2                                                                                                |
|                        | Machine Type        | e2-micro                                                                                          |
| OS and Storage         | Operating System    | Ubuntu                                                                                            |
|                        | Version             | Ubuntu 24.04 LTS (x86/64)                                                                         |
|                        | Boot disk Type      | Standard Persistent Disk                                                                          |
|                        | Size(GB)            | 30                                                                                                |
| Networking             | Allow HTTP traffic  | `True`                                                                                            |
|                        | Allow HTTPS traffic | `True`                                                                                            |
4. Finish the creation by clicking `Create` button.
5. Wait for the Creation of the virtual machine.
