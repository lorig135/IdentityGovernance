# Introduction
This guide shows you how to quickly install and get started with ForgeRock Access Review.

This guide is written for Access Review administrators who administer certification campaigns and Segregation-of-Duty (SOD) violation processes for their organizations. 

The following files, including the installer, are in the AReview-2.5.2.zip archive. The top-level directory
includes the following files and directories:
- install.sh: Linux installer
- install.bat: Windows installer
- governance.groovy: Common installer, invoked by both Linux and Windows installers
- governance.properties : Properties file that can be used in place of interactive input with the installers
- openidm : Files to be installed in the IDM home directory. These files include configuration files, scripts, workflows, CLI tools, user interface configuration, and file fragments that will be injected into existing files.

# Installation
1. Start ForgeRock® Identity Management (IDM). The installer will not work properly unless IDM is up and running. 
1. Unzip the AReview-2.5.2.zip to a temporary directory, then navigate to the directory the .zip file was unzipped in. t
1. Run the following command to initiate the installer:
- For Windows: 'install.bat [--properties filename | -p filename]'
- For Linux: './install.sh [--properties filename | -p filename]'

The command can be run with the following optional argument:
"- --properties or –p <location/of/properties/file>:". This command provides a properties file for script input. If you do not specify a properties file, you must input the following properties at run time:
- openidm_location: File location of IDM home directory.
- project_location: File location of IDM project directory, if used. This is an optional property that will default to the openidm_location if left blank.
- dg_installer_location: Location from where the installer is being run. 
- openidm_url: URL where IDM can be reached. This will often be the localhost.
- openidm_version: The version of IDM. This will either be 5.0, 5.5, 6.0, or 6.5.
- openidm_admin: User ID for user with openidm-admin role.
- openidm_admin_password: Password for IDM administrator.
- openidm_database_type: ‘MsSQL’ or ‘MySQL’ only for ForgeRock Access Review 2.5.1.
Note: Names are those found in the properties file. If a properties file is not used, equivalent input will be gathered directly from the installer.

The installer will print updates to the console until installation completes. 

1. Restart IDM. 
1. Enable Audit Event Handler: repo: 

 
 


