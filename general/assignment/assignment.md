# Install Apache on Web Servers

1. Install the httpd (Apache) package on your target web servers (one server should be ubuntu other should be RedHat).
       Ensure the Apache service is started and enabled to start on boot.

2. Create a custom HTML page (index.html) that will be served by Apache.
       The content of the page should include:
        ```A welcome message: "Welcome to {{ ansible_fqdn }}!"
           The date and time when the page was generated: "Generated on {{ ansible_date_time.iso8601 }}"
           Use Ansible's template module to deploy the HTML page. The file should be a Jinja2 template (index.html.j2).```

3. Create Users: Create a user named deploy on each server.
       Ensure the deploy user is added to the sudo group.
       Set a password for the deploy user.

4. Handler: Restart Apache on Changes
       If any configuration file or package change requires Apache to be restarted, create a handler to restart the Apache service.

5. Vault-encrypted Variables
       Create a Vault-encrypted variable file for sensitive data like deploy user password.
       Decrypt and use these variables in the playbook.

6. Convert the playbook to a role