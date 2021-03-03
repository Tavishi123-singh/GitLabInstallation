# GitLabInstallation
This is the ansible script that will install the GitLab on Linux server in one go.

Ansible is an open-source automation tool, or platform, used for IT tasks such as configuration management, application deployment, intraservice orchestration, and provisioning. Ansible works by connecting to your nodes and pushing out small programs, called "Ansible modules" to them. Ansible then executes these modules (over SSH by default), and removes them when finished. Your library of modules can reside on any machine, and there are no servers, daemons, or databases required. This tool is very simple to use yet powerful enough to automate complex multi-tier IT application environments.

* Ansible should be installed on the controller machine from where you run the playbook, if not then install it by these commands:
  $ sudo yum install python3-pip
  $ sudo pip3 install ansible

* Check the ansible version by:  $ ansible --version
* You have to create inventory and ansible.cfg files, can see the ansible documentation for the same.
* Also you have to copy id of target host for ssh:  $ ssh-copy-id username@hostname     or $ ssh-copy-id username@server_ip
* Always check that the target host is pingable by: $ ansible target_host -m ping

* Now, you are good to go run your playbook on the controller machine.

# Requirements for GitLab
* Operating Systems
  Supported Linux distributions
    - Ubuntu (16.04/18.04/20.04)
    - Debian (9/10)
    - CentOS (7/8)
    - openSUSE (Leap 15.1/Enterprise Server 12.2)
    - Red Hat Enterprise Linux (please use the CentOS packages and instructions)
    - Scientific Linux (please use the CentOS packages and instructions)
    - Oracle Linux (please use the CentOS packages and instructions)

* Software requirements:
  Ruby versions
    - From GitLab 13.6:
      Ruby 2.7 and later is required.
    - From GitLab 12.2:
      Ruby 2.6 and later is required.
  You must use the standard MRI implementation of Ruby. We love JRuby and Rubinius, but GitLab needs several Gems that have native extensions

* Go versions:
  The minimum required Go version is 1.13.

* Git versions
    - From GitLab 13.6:
      Git 2.29.x and later is required.
    - From GitLab 13.1:
      Git 2.24.x and later is required.
      Git 2.28.x and later is recommended.
      
* Node.js versions:
  Beginning in GitLab 12.9, we only support Node.js 10.13.0 or higher, and we have dropped support for Node.js 8. (Node.js 6 support was dropped in GitLab 11.8)
  We recommend Node 12.x, as it’s faster.
  
* Redis versions:
  GitLab 13.0 and later requires Redis version 4.0 or higher.
  Redis version 5.0 or higher is recommended
  
* Hardware requirements
    - Storage:
      The necessary hard drive space largely depends on the size of the repositories you want to store in GitLab but as a rule of thumb you should have at least as much free space as all your repositories combined take up. Apart from a local hard drive you can also mount a volume that supports the network file system (NFS) protocol. This volume might be located on a file server, a network attached storage (NAS) device, a storage area network (SAN) or on an Amazon Web Services (AWS) Elastic Block Store (EBS) volume. If you have enough RAM and a recent CPU the speed of GitLab is mainly limited by hard drive seek times. Having a fast drive (7200 RPM and up) or a solid state drive (SSD) will improve the responsiveness of GitLab.
 
    - CPU:
      CPU requirements are dependent on the number of users and expected workload. Your exact needs may be more, depending on your workload. Your workload is influenced by factors such as - but not limited to - how active your users are, how much automation you use, mirroring, and repository/change size. The following is the recommended minimum CPU hardware guidance for a handful of example GitLab user base sizes. 
      4 cores is the recommended minimum number of cores and supports up to 500 users
      8 cores supports up to 1000 users
      
    - Memory:
      Memory requirements are dependent on the number of users and expected workload. Your exact needs may be more, depending on your workload. Your workload is influenced by factors such as - but not limited to - how active your users are, how much automation you use, mirroring, and repository/change size. The following is the recommended minimum Memory hardware guidance for a handful of example GitLab user base sizes.
      4GB RAM is the required minimum memory size and supports up to 500 users
      8GB RAM supports up to 1000 users
      
    - Database:
      PostgreSQL is the only supported database, which is bundled with the Omnibus GitLab package. You can also use an external PostgreSQL database. Support for MySQL was removed in GitLab 12.1. Existing users using GitLab with MySQL/MariaDB are advised to migrate to PostgreSQL before upgrading.

    - PostgreSQL Requirements:
      The server running PostgreSQL should have at least 5-10 GB of storage available, though the exact requirements depend on the number of users. We highly recommend users to use the minimum PostgreSQL versions specified below as these are the versions used for development and testing.

        + GitLab version: 10.0  Minimum PostgreSQL version: 9.6
        + GitLab version: 13.0  Minimum PostgreSQL version: 11
