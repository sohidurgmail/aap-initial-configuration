# aap-initial-configuration
This Repo is to configure AAP after installation


In the world of IT automation, Ansible has emerged as a powerful tool for streamlining tasks and orchestrating complex systems. With the release of Ansible Automation Platform (AAP) 2.X, managing automation workflows has become even more efficient. In this blog post, we'll explore how to configure a newly deployed AAP 2.X instance using API calls directly from a playbook. By following these steps, you'll be able to set up your automation environment swiftly and seamlessly.
Of course, in most cases you will use a collection such as ansible.controller (Red Hat certified) or infra.controller_configuration (Red Hat validated) as a more flexible option to configure AAP. However for cases when collections are not available, such as initial configuration right after setup or environments with special security requirements where external collections are not approved for use, you will have no choice other than utilizing API calls.

Prerequisites:
Before diving into the configuration process, ensure you meet the following prerequisites:

Ansible Automation Platform 2.X: Ensure that Ansible Automation Platform 2.X that is being configured was installed without errors and is accessible along with Private Automation Hub. AAP serves as an end-to-end automation platform to configure systems and orchestrate advanced workflows.

Ansible package: Latest release of  Ansible (2.9 or later) must be installed on the host where the playbook will run. If you haven't already installed Ansible, make sure to set it up on your system before proceeding further. If you are running the playbook on the same host that was used for AAP installation, Ansible package will already be there.

GitHub Credentials: You'll need your GitHub username and personal access token to authenticate with GitHub and access repositories. The examples below assume the repository with AAP configuration is not public.

GitHub Repository: Prepare the GitHub repository URL where your Ansible playbook and related files are stored. This repository will be used for version control and synchronization with your AAP environment.

Collections Tarballs: If you are going to import any collections into Private Automation Hub, make sure collection tarball files are accessible by the playbook. Collections contain reusable automation content and modules necessary for various tasks within your automation workflows.

Ansible Installation Inventory File: Ensure you have an inventory file containing the necessary configuration details, such as host addresses and groupings, for your Ansible installation. This can be the same inventory file you used for AAP installation and it is expected to be located in the same folder as the playbook containing the examples below.
