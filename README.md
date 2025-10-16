Esta version resuelve el problema "Precheck fails on "Validating whether source Org VDC placement policies are present in target PVDC" against newer versions of vCloud Director"
Cambia el archivo Yaml de la migracion, donde se agrega los siguientes campos:
Trabajaron en esta solucion: Christian Gonzalez y Juan Pablo Taño
Pyxis Tech - Uruguay.
---
VCloudDirector:
  ipAddress: # IP/FQDN of VMware Cloud Director
  username: #  VMware Cloud Director system administrator login name
  verify: # Certificate validation enabled
  forceApiVersion: 38.1 # Este campo fuerza el uso de una version de API especifica y resuelve el problema.

OrgVDC: # (optional) List of NSX-V backed organization VDC(s) to be assessed
   

Organization: # (optional) List of names of the organization(s) to be validated
  


Common:
  CertificatePath: 

############################################
VCloudDirector:
  Common:
    ipAddress: # IP/FQDN of VMware Cloud Director
    username:  # VMware Cloud Director system administrator login name
    verify:  # Certificate validation enabled
    forceApiVersion: 38.1 #Este campo fuerza el uso de una version de API especifica y resuelve el problema.
  Organization:
    OrgName:  # Short name of the organization containing Org VDC to be migrated
  SourceOrgVDC:
    # Single/multiple source Org VDCs in the form of a list that needs to be migrated
    ....



    ##### ENGLISH ####

This release resolves the issue "Precheck fails on 'Validating whether source Org VDC placement policies are present in target PVDC' against newer versions of vCloud Director."
It changes the migration's Yaml file, adding the following fields:
They worked on this solution: Christian Gonzalez and Juan Pablo Taño
Pyxis Tech - Uruguay.
---
vCloudDirector:
ipAddress: # IP/FQDN of VMware Cloud Director
username: # VMware Cloud Director system administrator login name
verify: # Certificate validation enabled
forceApiVersion: 38.1 # This field forces the use of a specific API version and resolves the issue.

OrgVDC: # (optional) List of NSX-V backed organization VDC(s) to be assessed


Organization: # (optional) List of names of the organization(s) to be validated



Common: 
CertificatePath:

############################################
VCloudDirector: 
Common: 
ipAddress: # IP/FQDN of VMware Cloud Director 
username: # VMware Cloud Director system administrator login name 
verify: # Certificate validation enabled 
forceApiVersion: 38.1 #This field forces the use of a specific API version and resolves the issue. 
Organization: 
OrgName: # Short name of the organization containing Org VDC to be migrated 
SourceOrgVDC: 
# Single/multiple source Org VDCs in the form of a list that needs to be migrated 
....
