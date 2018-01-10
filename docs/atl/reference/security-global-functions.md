---
title: "전역 함수를 보안 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlsecurity/ATL::AtlGetDacl
- atlsecurity/ATL::AtlSetDacl
- atlsecurity/ATL::AtlGetGroupSid
- atlsecurity/ATL::AtlSetGroupSid
- atlsecurity/ATL::AtlGetOwnerSid
- atlsecurity/ATL::AtlSetOwnerSid
- atlsecurity/ATL::AtlGetSacl
- atlsecurity/ATL::AtlSetSacl
- atlsecurity/ATL::AtlGetSecurityDescriptor
dev_langs: C++
helpviewer_keywords:
- SIDs [C++], modifying SID objects
- ACL object global functions
- security IDs [C++]
ms.assetid: 6a584bfe-16b7-47f4-8439-9c789c41567a
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c1439fcf15a9359d3a548945edc76c1ddcf8675f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="security-global-functions"></a>보안 전역 함수
이러한 함수는 SID 및 ACL 개체를 수정 하기 위한 지원을 제공 합니다.  
  
> [!IMPORTANT]
>  다음 표에 나열 된 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
|||  
|-|-|  
|[AtlGetDacl](#atlgetdacl)|지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.|  
|[AtlSetDacl](#atlsetdacl)|지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.|  
|[AtlGetGroupSid](#atlgetgroupsid)|개체의 그룹 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.|  
|[AtlSetGroupSid](#atlsetgroupsid)|개체의 그룹 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.|  
|[AtlGetOwnerSid](#atlgetownersid)|개체의 소유자 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.|  
|[AtlSetOwnerSid](#atlsetownersid)|개체의 소유자 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.|  
|[AtlGetSacl](#atlgetsacl)|지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.|  
|[AtlSetSacl](#atlsetsacl)|지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.|  
|[AtlGetSecurityDescriptor](#atlgetsecuritydescriptor)|지정된 개체의 보안 설명자를 검색하려면 이 함수를 호출합니다.|  

## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlgetdacl"></a>AtlGetDacl  
 지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlGetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CDacl* pDacl) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 검색할에 대 한 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 `pDacl`  
 검색 된 보안 정보를 포함 하는 DACL 개체에 대 한 포인터입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에서 경우 어설션 오류가 발생 합니다 `hObject` 또는 `pDacl` 올바르지 않습니다.  
  
##  <a name="atlsetdacl"></a>AtlSetDacl  
 지정된 개체의 DACL(임의 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlSetDacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CDacl& rDacl,
    DWORD dwInheritanceFlowControl = 0) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 설정 하려는 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 `rDacl`  
 새 보안 정보를 포함 하는 DACL 합니다.  
  
 `dwInheritanceFlowControl`  
 상속 흐름 제어 합니다. 이 값은 0 (기본값) 이면 PROTECTED_DACL_SECURITY_INFORMATION 또는 UNPROTECTED_DACL_SECURITY_INFORMATION 일 수 있습니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 발생 하는 경우 발생 합니다 `hObject` 유효 하지 않을 경우 또는 `dwInheritanceFlowControl` 허용 되는 세 가지 값 중 하나가 아닙니다.  
### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlgetgroupsid"></a>AtlGetGroupSid  
 개체의 그룹 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlGetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 검색할 수 있는 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 `pSid`  
 에 대 한 포인터는 `CSid` 새 보안 정보를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlsetgroupsid"></a>AtlSetGroupSid  
 개체의 그룹 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlSetGroupSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 설정 하려는 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 `rSid`  
 `CSid` 새 보안 정보를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlgetownersid"></a>AtlGetOwnerSid  
 개체의 소유자 보안 식별자(SID)를 검색하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlGetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSid* pSid) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 검색할 수 있는 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 `pSid`  
 에 대 한 포인터는 `CSid` 새 보안 정보를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlsetownersid"></a>AtlSetOwnerSid  
 개체의 소유자 보안 식별자(SID)를 설정하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlSetOwnerSid(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSid& rSid) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 설정 하려는 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 `rSid`  
 `CSid` 새 보안 정보를 포함 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlgetsacl"></a>AtlGetSacl  
 지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 검색하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlGetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    CSacl* pSacl,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 검색할 수 있는 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 `pSacl`  
 검색 된 보안 정보를 포함 하는 SACL 개체에 대 한 포인터입니다.  
  
 `bRequestNeededPrivileges`  
 True 이면 함수는 se_security_name 권한을 권한을 설정 하 고 완료에서 복원 하려고 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 경우 `AtlGetSacl` 많은 다른 개체를 여러 번 호출 되는 것 보다 효율적으로 함수를 호출 하기 전에 한 번 se_security_name 권한을 권한을 설정 하려면 `bRequestNeededPrivileges` false로 설정 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlsetsacl"></a>AtlSetSacl  
 지정된 개체의 SACL(시스템 액세스 제어 목록) 정보를 설정하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlSetSacl(
    HANDLE hObject,
    SE_OBJECT_TYPE ObjectType,
    const CSacl& rSacl,
    DWORD dwInheritanceFlowControl = 0,
    bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `hObject`  
 보안 정보를 설정 하려는 개체에 대 한 핸들입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형은 `hObject` 매개 변수입니다.  
  
 *rSacl*  
 새 보안 정보가 포함 된 SACL 합니다.  
  
 `dwInheritanceFlowControl`  
 상속 흐름 제어 합니다. 이 값은 0 (기본값) 이면 PROTECTED_SACL_SECURITY_INFORMATION 또는 UNPROTECTED_SACL_SECURITY_INFORMATION 일 수 있습니다.  
  
 `bRequestNeededPrivileges`  
 True 이면 함수는 se_security_name 권한을 권한을 설정 하 고 완료에서 복원 하려고 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 디버그 빌드에 어설션 오류가 발생 하는 경우 발생 합니다 `hObject` 유효 하지 않을 경우 또는 `dwInheritanceFlowControl` 허용 되는 세 가지 값 중 하나가 아닙니다.  
  
 경우 `AtlSetSacl` 많은 다른 개체를 여러 번 호출 되는 것 보다 효율적으로 함수를 호출 하기 전에 한 번 se_security_name 권한을 권한을 설정 하려면 `bRequestNeededPrivileges` false로 설정 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 

##  <a name="atlgetsecuritydescriptor"></a>AtlGetSecurityDescriptor  
 지정된 개체의 보안 설명자를 검색하려면 이 함수를 호출합니다.  
  
> [!IMPORTANT]
>  이 함수는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
```
inline bool AtlGetSecurityDescriptor(
    LPCTSTR pszObjectName,
    SE_OBJECT_TYPE ObjectType,
    CSecurityDesc* pSecurityDescriptor,
    SECURITY_INFORMATION requestedInfo = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION,
 bool bRequestNeededPrivileges = true) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 *pszObjectName*  
 보안 정보를 검색할 수 있는 개체의 이름을 지정 하는 null로 끝나는 문자열에 대 한 포인터입니다.  
  
 `ObjectType`  
 값을 지정 된 [SE_OBJECT_TYPE](http://msdn.microsoft.com/library/windows/desktop/aa379593) 로 식별 된 개체의 형식을 나타내는 열거형의 *pszObjectName* 매개 변수입니다.  
  
 *pSecurityDescriptor*  
 요청 된 보안 설명자를 수신 하는 개체입니다.  
  
 *requestedInfo*  
 집합이 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) 비트 검색할 보안 정보 형식을 나타내는 플래그입니다. 이 매개 변수는 다음 값의 조합 수 있습니다.  
  
 `bRequestNeededPrivileges`  
 True 이면 함수는 se_security_name 권한을 권한을 설정 하 고 완료에서 복원 하려고 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 경우 `AtlGetSecurityDescriptor` 많은 다른 개체를 여러 번 호출 되는 것 보다 효율적으로 함수를 호출 하기 전에 한 번 se_security_name 권한을 권한을 설정 하려면 `bRequestNeededPrivileges` false로 설정 합니다.  

### <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h 
   
## <a name="see-also"></a>참고 항목  
 [함수](../../atl/reference/atl-functions.md)
