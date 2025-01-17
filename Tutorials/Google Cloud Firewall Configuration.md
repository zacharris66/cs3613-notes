In order to open up additional ports outside of the HTTP and HTTPs default ports we need to add those to our particular virtual machines. In order to do this please follow the steps below to add for example incoming connections on port 8000:

## Create Firewall Rule
1. Use the Search bar for `Firewall` and select the option for `Firewall - VPC Network`
2. Click `Create Firewall Rule` button at the top of the page.
3. Name your rule.
	- Make this name descriptive of what you are trying to do, for this particular instance we are going to name our rule `django-dev-ingress`
4. Direction of traffic should be set to `Ingress`
5. Action on match: `Allow`
6. Targets: `Specified target tags`
7. Target Tags: Create a tag that is descriptive for this example you can use `django-dev`
8. Source Filter: `IPv4 ranges`
9. Source IPv4 ranges: `0.0.0.0/0`
10. Protocols and ports: `Specified protocols and ports`
11. TCP: `True`
12. TCP Ports: Enter the port you want this to accept for this tutorial `8000`
13. Click Create

## Add Rule to Virtual Machine
1. Use the Navigation Menu and Select Compute Engine
2. Select the Virtual Machine to add our rule to, in our example `astate-webdev`
3. Click the `Edit` button at the top
4. Scroll down to the Networking Section and add our tag to the `Network Tags` section.
5. Click Save
