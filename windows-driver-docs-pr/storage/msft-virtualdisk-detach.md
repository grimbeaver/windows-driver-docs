---
title: Detach Method of the MSFT_VirtualDisk Class
description: Detaches a storage spaces-based virtual disk from a computer.
ms.assetid: ED70182D-C5FF-4BB7-9CDC-FDA4C60BB36D
keywords:
- Detach method Windows Storage Management API
- Detach method Windows Storage Management API , MSFT_VirtualDisk class
- MSFT_VirtualDisk class Windows Storage Management API , Detach method
topic_type:
- apiref
ms.topic: reference
api_name:
- MSFT_VirtualDisk.Detach
api_location:
- Root\Microsoft\Windows\Storage
api_type:
- COM
ms.date: 05/31/2018
---

# Detach method of the MSFT\_VirtualDisk class

Detaches a storage spaces-based virtual disk from a computer.

## Syntax


```mof
UInt32 Detach(
  [in]  String StorageNodeName,
  [out] String ExtendedStatus
);
```



## Parameters

 

*StorageNodeName* \[in\]
 

The name of the storage node.

 

*ExtendedStatus* \[out\]
 

A string that contains an embedded [**MSFT\_StorageExtendedStatus**](msft-storageextendedstatus.md) object.

This parameter allows the storage provider to return extended (implementation-specific) error information.

 

## Return value

 

**Success** (0)
 

**Not Supported** (1)
 

**Unspecified Error** (2)
 

**Timeout** (3)
 

**Failed** (4)
 

**Invalid Parameter** (5)
 

**Access denied** (40001)
 

**There are not enough resources to complete the operation.** (40002)
 

**Cannot connect to the storage provider.** (46000)
 

**The storage provider cannot connect to the storage subsystem.** (46001)
 

**The storage pool could not complete the operation because its health or operational status does not permit it.** (48006)
 

**The storage pool could not complete the operation because its configuration is read-only.** (48007)
 

**The virtual disk could not complete the operation because another computer controls its configuration.** (50002)
 

**The virtual disk could not complete the operation because its health or operational status does not permit it.** (50003)
 

**The virtual disk could not complete the operation because its Manual Attach status does not permit it.** (50004)
 

## Remarks

This operation is similar to [**Hide**](msft-virtualdisk-hide.md). However, there is no need for target and initiator configuration, because everything is done locally. Detaching a storage space will cause its corresponding disk object to be surprise-removed from the system. Note that detaching can happen in response to certain failure and warning conditions (such as failing redundancy, or thin provisioning capacity limits being reached).

## Requirements



| Requirement | Value |
|-------------------------------------|-------------------------------------------------------------------------------------------|
| Minimum supported client | Windows 8 \[desktop apps only\]                                                |
| Minimum supported server | Windows Server 2012 \[desktop apps only\]                                      |
| Namespace                | Root\\Microsoft\\Windows\\Storage                                              |
| MOF                      |  Storagewmi.mof  |



## See also

 

[**MSFT\_VirtualDisk**](msft-virtualdisk.md)
 

 

 





