# 0x17. Web stack debugging #3

## Task Overview

This task involves debugging a WordPress website running on a LAMP stack using `strace` and Puppet on Ubuntu 14.04 LTS. The goal is to identify and fix issues with the web server's configuration and ensure that the site is correctly displayed.

## Steps to Complete

1. **Install Puppet and Puppet Lint**:
   - Ensure Puppet is installed on the server.
   - Install the Puppet Lint gem using `sudo gem install puppet-lint -v 2.1.1`.

2. **Create the Puppet Manifest**:
   - The Puppet manifest file `0-strace_is_your_friend.pp` was created to manage the web server configuration.
   - This manifest updates the content of `/var/www/html/index.html` to display a custom page.

3. **Apply the Puppet Manifest**:
   - Apply the Puppet manifest using the command: `sudo /opt/puppetlabs/bin/puppet apply 0-strace_is_your_friend.pp`.
   - Verify that the content of `/var/www/html/index.html` has been updated successfully.

4. **Verify the Web Page**:
   - Check the web page served by Apache to ensure that it displays the updated content correctly.

## Puppet Manifest Content

The Puppet manifest (`0-strace_is_your_friend.pp`) includes the following configuration:

- **File Resource**: Manages the content of `/var/www/html/index.html`.
- **Content**: The content of the file was updated to provide information about Apache configuration and document roots.

## Troubleshooting

- If you encounter any errors, ensure that Puppet is correctly installed and that the manifest file syntax is correct.
- Verify that the Apache service is running and accessible.
- Check the Puppet logs for detailed error messages if the apply command fails.

## References

- [Puppet Documentation](https://puppet.com/docs/puppet/latest/puppet_index.html)
- [Apache Documentation](https://httpd.apache.org/docs/)

---
