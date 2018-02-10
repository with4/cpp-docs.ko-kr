---
title: "CPrivateObjectSecurityDesc 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
dev_langs:
- C++
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4845d652d2b1dceb8ffc0f2772f88565eb81e29
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2018
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc 클래스
이 클래스는 private 개체에서 보안 설명자 개체를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|생성자입니다.|  
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|보안 설명자 및 해당 액세스 제어 목록 (Acl)을 지 원하는 (Ace) 상속 가능한 액세스 제어 항목의 자동 전파 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CPrivateObjectSecurityDesc::Create](#create)|할당 하 고 호출 하는 리소스 관리자가 만든 private 개체에 대 한 자기 상대적 보안 설명자를 초기화할이 메서드를 호출 합니다.|  
|[CPrivateObjectSecurityDesc::Get](#get)|개인 개체의 보안 설명자에서 정보를 검색 하려면이 메서드를 호출 합니다.|  
|[CPrivateObjectSecurityDesc::Set](#set)|Private 개체의 보안 설명자를 수정 하려면이 메서드를 호출 합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>설명  
 이 클래스에서 파생 된 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)를 만들고 private 개체의 보안 설명자를 관리 하기 위한 메서드를 제공 합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows sdk에서입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="converttoautoinherit"></a>  CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 보안 설명자 및 해당 액세스 제어 목록 (Acl)을 지 원하는 (Ace) 상속 가능한 액세스 제어 항목의 자동 전파 형식으로 변환 하려면이 메서드를 호출 합니다.  
  
```
bool ConvertToAutoInherit(  
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pParent`  
 에 대 한 포인터는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 개체의 부모 컨테이너를 참조 하는 개체입니다. 부모 컨테이너가 없는 경우이 매개 변수는 NULL입니다.  
  
 `ObjectType`  
 에 대 한 포인터는 **GUID** 현재 개체와 연결 된 개체의 형식을 식별 하는 구조입니다. 설정 `ObjectType` 을 개체에는 GUID가 없는 경우 NULL입니다.  
  
 `bIsDirectoryObject`  
 새 개체가 다른 개체를 포함할 수 있는지 여부를 지정 합니다. 값이 true 인 새 개체 컨테이너 임을 나타냅니다. 값이 false 새 개체 컨테이너 임을 나타냅니다.  
  
 `GenericMapping`  
 에 대 한 포인터는 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) 개체에 대 한 특정 권한 각 제네릭 오른쪽에서 매핑을 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 Ace의 임의 액세스 제어에서 목록 (DACL) 여부를 확인 하려고 하는 메서드 및 현재 보안 설명자의 시스템 액세스 제어 목록 (SACL) 부모 보안 설명자에서 상속 되었습니다. 호출 된 [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403) 함수입니다.  
  
##  <a name="cprivateobjectsecuritydesc"></a>  CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 생성자입니다.  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>설명  
 초기화는 `CPrivateObjectSecurityDesc` 개체입니다.  
  
##  <a name="dtor"></a>  CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc  
 소멸자입니다.  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>설명  
 소멸자는 할당 된 모든 리소스를 해제 하 고 개인 개체의 보안 설명자를 삭제 합니다.  
  
##  <a name="create"></a>  CPrivateObjectSecurityDesc::Create  
 할당 하 고 호출 하는 리소스 관리자가 만든 private 개체에 대 한 자기 상대적 보안 설명자를 초기화할이 메서드를 호출 합니다.  
  
```
bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `pParent`  
 에 대 한 포인터는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 새 개체가 생성 되는 부모 디렉터리를 참조 하는 개체입니다. 부모 디렉터리가 없는 경우 NULL로 설정 합니다.  
  
 `pCreator`  
 개체의 작성자에 의해 제공 된 보안 설명자에 대 한 포인터입니다. 개체의 작성자는 새 개체에 대 한 보안 정보를 명시적으로 통과 하지 못하는 경우이 매개 변수를 NULL로 설정 합니다.  
  
 `bIsDirectoryObject`  
 새 개체가 다른 개체를 포함할 수 있는지 여부를 지정 합니다. 값이 true 인 새 개체 컨테이너 임을 나타냅니다. 값이 false 새 개체 컨테이너 임을 나타냅니다.  
  
 `Token`  
 에 대 한 참조는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체가 생성 되 고 대신 클라이언트 프로세스에 대 한 개체입니다.  
  
 `GenericMapping`  
 에 대 한 포인터는 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) 개체에 대 한 특정 권한 각 제네릭 오른쪽에서 매핑을 지정 하는 구조입니다.  
  
 `ObjectType`  
 에 대 한 포인터는 **GUID** 현재 개체와 연결 된 개체의 형식을 식별 하는 구조입니다. 설정 `ObjectType` 을 개체에는 GUID가 없는 경우 NULL입니다.  
  
 *bIsContainerObject*  
 새 개체가 다른 개체를 포함할 수 있는지 여부를 지정 합니다. 값이 true 인 새 개체 컨테이너 임을 나타냅니다. 값이 false 새 개체 컨테이너 임을 나타냅니다.  
  
 `AutoInheritFlags`  
 액세스 제어 항목 (Ace)에서 상속 되는 방식을 제어 하는 비트 플래그 집합이 `pParent`합니다. 참조 [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) 내용을 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드를 호출 [CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405) 또는 [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581)합니다.  
  
 두 번째 방법은 Ace 상속 되는 방식을 제어 하거나 새 개체의 GUID 개체 형식 지정을 허용 합니다.  
  
> [!NOTE]
>  자기 상대적 보안 설명자는 인접 한 메모리 블록의 모든 보안 정보를 저장 하는 보안 설명자가입니다.  
  
##  <a name="get"></a>  CPrivateObjectSecurityDesc::Get  
 개인 개체의 보안 설명자에서 정보를 검색 하려면이 메서드를 호출 합니다.  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `si`  
 검색할 보안 설명자의 부분을 나타내는 비트 플래그의 집합입니다. 이 값의 조합 수는 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) 비트 플래그입니다.  
  
 `pResult`  
 에 대 한 포인터는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 지정 된 보안 설명자에서 요청 된 정보의 복사본을 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 보안 설명자에는 구조와 연결 된 데이터는 보안 가능한 개체에 대 한 보안 정보를 포함 하는 합니다.  
  
##  <a name="operator_eq"></a>  CPrivateObjectSecurityDesc::operator =  
 대입 연산자입니다.  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `CPrivateObjectSecurityDesc` 현재 개체에 할당할 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CPrivateObjectSecurityDesc` 개체입니다.  
  
##  <a name="set"></a>  CPrivateObjectSecurityDesc::Set  
 Private 개체의 보안 설명자를 수정 하려면이 메서드를 호출 합니다.  
  
```
bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `si`  
 설정할 보안 설명자의 부분을 나타내는 비트 플래그의 집합입니다. 이 값의 조합 수는 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) 비트 플래그입니다.  
  
 *수정*  
 에 대 한 포인터는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 개체입니다. 이 보안 설명자의 부분으로 표시는 `si` 매개 변수 개체의 보안 설명자에 적용 됩니다.  
  
 `GenericMapping`  
 에 대 한 포인터는 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) 개체에 대 한 특정 권한 각 제네릭 오른쪽에서 매핑을 지정 하는 구조입니다.  
  
 `Token`  
 에 대 한 참조는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체가 생성 되 고 대신 클라이언트 프로세스에 대 한 개체입니다.  
  
 `AutoInheritFlags`  
 액세스 제어 항목 (Ace)에서 상속 되는 방식을 제어 하는 비트 플래그 집합이 `pParent`합니다. 참조 [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) 내용을 확인 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>설명  
 두 번째 방법은 Ace 상속 되는 방식을 제어 하거나 개체의 GUID 개체 형식 지정을 허용 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc 클래스](../../atl/reference/csecuritydesc-class.md)
