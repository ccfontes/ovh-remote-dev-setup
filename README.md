# ovh-remote-dev-setup

## Create and destroy an instance

Follow [these](https://sdorsett.github.io/post/2018-08-10-using-the-openstack-cli-to-create-a-server-on-ovh-public-cloud/) setup instructions in order to create and destroy an instance. Skip the OpenStack install instructions, and do the following instead:
```
alias openstack='docker run -it --rm -v ~/.ssh:$HOME/.ssh:ro -e OS_AUTH_URL -e OS_IDENTITY_API_VERSION -e OS_USER_DOMAIN_NAME -e OS_PROJECT_DOMAIN_NAME -e OS_TENANT_ID -e OS_TENANT_NAME -e OS_PROJECT_DOMAIN_NAME -e OS_USERNAME -e OS_PASSWORD -e OS_REGION_NAME ullbergm/openstack-client:latest openstack'
```

## Staying out of trouble
  - If you're getting a `resource not found` error when running `cloudstack server create`, change to a region that allows provisioning of specified flavor or image.
  - Import ssh key into the same region as specified by `OS_REGION_NAME`.