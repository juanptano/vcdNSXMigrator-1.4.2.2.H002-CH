# 🧩 vCloud Director Migration YAML Update

### Versión que soluciona el error:
> **"Precheck fails on 'Validating whether source Org VDC placement policies are present in target PVDC'"**  
> (en versiones recientes de VMware Cloud Director)

---

## 🚀 Descripción

Esta versión incluye una corrección en el archivo de configuración **YAML** utilizado durante el proceso de migración de **vCloud Director**, agregando un nuevo campo que fuerza el uso de una versión específica de API.  
Esto garantiza la compatibilidad con versiones más recientes de **vCloud Director** y evita errores durante la validación de las políticas de ubicación de los **Org VDC**.

---

## ✨ Cambios principales

Se agrega el campo:

```yaml
forceApiVersion: 38.1  # Este campo fuerza el uso de una versión de API específica y resuelve el problema.
```

---

## 🧱 Ejemplo de configuración YAML

### Estructura básica

```yaml
VCloudDirector:
  ipAddress: # IP/FQDN de VMware Cloud Director
  username: # Usuario administrador del sistema en VMware Cloud Director
  verify: # Validación del certificado habilitada
  forceApiVersion: 38.1 # Este campo fuerza el uso de una versión de API específica y resuelve el problema.

OrgVDC: # (opcional) Lista de VDC(s) de organización respaldados por NSX-V a evaluar

Organization: # (opcional) Lista de nombres de las organizaciones a validar

Common:
  CertificatePath:
```

---

### Estructura extendida (para escenarios de migración)

```yaml
VCloudDirector:
  Common:
    ipAddress: # IP/FQDN de VMware Cloud Director
    username:  # Usuario administrador del sistema en VMware Cloud Director
    verify:  # Validación del certificado habilitada
    forceApiVersion: 38.1 # Este campo fuerza el uso de una versión de API específica y resuelve el problema.

  Organization:
    OrgName:  # Nombre corto de la organización que contiene el Org VDC a migrar

  SourceOrgVDC:
    # Lista única o múltiple de Org VDCs fuente que se deben migrar
    ...
```

---

## 👨‍💻 Contribuyeron en esta solución

- **Christian Gonzalez**  
- **Juan Pablo Taño**  

**Pyxis Tech - Uruguay 🇺🇾**

---

## 🌍 English Version

### Issue Fixed:
> **"Precheck fails on 'Validating whether source Org VDC placement policies are present in target PVDC'"**  
> (in newer versions of VMware Cloud Director)

---

## 🚀 Description

This release updates the **migration YAML configuration**, adding a new field to force a specific **API version**.  
This resolves compatibility issues and prevents validation errors when checking Org VDC placement policies.

---

## ✨ Main Change

```yaml
forceApiVersion: 38.1  # This field forces the use of a specific API version and resolves the issue.
```

---

## 🧱 Basic YAML Example

```yaml
vCloudDirector:
  ipAddress: # IP/FQDN of VMware Cloud Director
  username: # VMware Cloud Director system administrator login name
  verify: # Certificate validation enabled
  forceApiVersion: 38.1 # This field forces the use of a specific API version and resolves the issue.

OrgVDC: # (optional) List of NSX-V backed organization VDC(s) to be assessed

Organization: # (optional) List of names of the organization(s) to be validated

Common:
  CertificatePath:
```

---

### Extended Example (for migration)

```yaml
VCloudDirector:
  Common:
    ipAddress: # IP/FQDN of VMware Cloud Director
    username:  # VMware Cloud Director system administrator login name
    verify:  # Certificate validation enabled
    forceApiVersion: 38.1 # This field forces the use of a specific API version and resolves the issue.

  Organization:
    OrgName:  # Short name of the organization containing Org VDC to be migrated

  SourceOrgVDC:
    # Single or multiple source Org VDCs in the form of a list that need to be migrated
    ...
```

---

## 🏷️ Credits

Developed by **Christian Gonzalez** & **Juan Pablo Taño**  
**Pyxis Tech - Uruguay**
