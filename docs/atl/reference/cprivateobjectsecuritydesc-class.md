---
title: "CPrivateObjectSecurityDesc 클래스 | Microsoft 문서"
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
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 154a4229f8963d3081e6e0518354d17968ee0e20
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc 클래스
이 클래스는 private 개체 보안 설명자 개체를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|생성자입니다.|  
|[CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|보안 설명자 및 액세스 제어 목록 (Acl)를 상속 가능한 액세스 제어 항목 (Ace)의 자동 전파를 지원할 수 있는 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CPrivateObjectSecurityDesc::Create](#create)|할당 및 자기 상대적 보안 설명자를 호출 하는 리소스 관리자에서 만든 개인 개체를 초기화 하려면이 메서드를 호출 합니다.|  
|[CPrivateObjectSecurityDesc::Get](#get)|개인 개체의 보안 설명자에서 정보를 검색 하려면이 메서드를 호출 합니다.|  
|[CPrivateObjectSecurityDesc::Set](#set)|전용 개체의 보안 설명자를 수정 하려면이 메서드를 호출 합니다.|  
  
### <a name="operators"></a>연산자  
  
|||  
|-|-|  
|[연산자 =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스에서 파생 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)를 만들고 전용 개체의 보안 설명자를 관리 하기 위한 메서드를 제공 합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="converttoautoinherit"></a>CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 보안 설명자 및 액세스 제어 목록 (Acl)를 상속 가능한 액세스 제어 항목 (Ace)의 자동 전파를 지원할 수 있는 형식으로 변환 하려면이 메서드를 호출 합니다.  
  
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
 에 대 한 포인터는 **GUID** 현재 개체와 관련 된 개체의 형식을 식별 하는 구조입니다. 설정 `ObjectType` 개체에는 GUID가 없는 경우 null입니다.  
  
 `bIsDirectoryObject`  
 새 개체가 다른 개체를 포함할 수 있는지 여부를 지정 합니다. 값이 true 이면 새 개체가 컨테이너 인지를 나타냅니다. False 값을 새 개체가 컨테이너 인지를 나타냅니다.  
  
 `GenericMapping`  
 에 대 한 포인터는 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) 개체에 대 한 특정 권한을 갖도록 각 제네릭 오른쪽에서 매핑을 지정 하는 구조입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 임의 액세스 제어의 Ace 목록 (DACL) 여부를 확인 하려고 하는 메서드 및 현재 보안 설명자의 시스템 액세스 제어 목록 (SACL) 부모 보안 설명자에서 상속 되었습니다. 호출 하 여 [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403) 함수입니다.  
  
##  <a name="cprivateobjectsecuritydesc"></a>CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 생성자입니다.  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>주의  
 초기화는 `CPrivateObjectSecurityDesc` 개체입니다.  
  
##  <a name="dtor"></a>CPrivateObjectSecurityDesc:: ~ CPrivateObjectSecurityDesc  
 소멸자입니다.  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>주의  
 소멸자는 할당 된 모든 리소스를 해제 하 고 개인 개체의 보안 설명자를 삭제 합니다.  
  
##  <a name="create"></a>CPrivateObjectSecurityDesc::Create  
 할당 및 자기 상대적 보안 설명자를 호출 하는 리소스 관리자에서 만든 개인 개체를 초기화 하려면이 메서드를 호출 합니다.  
  
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
 개체의 작성자가 제공 하는 보안 설명자에 대 한 포인터입니다. 개체의 작성자는 새 개체에 대 한 보안 정보를 명시적으로 통과 하지 못하는 경우이 매개 변수를 NULL로 설정 합니다.  
  
 `bIsDirectoryObject`  
 새 개체가 다른 개체를 포함할 수 있는지 여부를 지정 합니다. 값이 true 이면 새 개체가 컨테이너 인지를 나타냅니다. False 값을 새 개체가 컨테이너 인지를 나타냅니다.  
  
 `Token`  
 에 대 한 참조는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 만든 대신 클라이언트 프로세스에 대 한 개체입니다.  
  
 `GenericMapping`  
 에 대 한 포인터는 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) 개체에 대 한 특정 권한을 갖도록 각 제네릭 오른쪽에서 매핑을 지정 하는 구조입니다.  
  
 `ObjectType`  
 에 대 한 포인터는 **GUID** 현재 개체와 관련 된 개체의 형식을 식별 하는 구조입니다. 설정 `ObjectType` 개체에는 GUID가 없는 경우 null입니다.  
  
 *bIsContainerObject*  
 새 개체가 다른 개체를 포함할 수 있는지 여부를 지정 합니다. 값이 true 이면 새 개체가 컨테이너 인지를 나타냅니다. False 값을 새 개체가 컨테이너 인지를 나타냅니다.  
  
 `AutoInheritFlags`  
 액세스 제어 항목 (Ace)에서 상속 되는 방식을 제어 하는 비트 플래그 집합 `pParent`합니다. 참조 [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 호출 [CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405) 또는 [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581)합니다.  
  
 새 개체의 GUID 개체 유형을 지정할 수 또는 Windows 2000을 실행 하는 시스템에서 사용할 수 있고 이상만 Ace 상속 되는 방식을 제어 하는 두 번째 방법입니다.  
  
> [!NOTE]
>  자기 상대적 보안 설명자는 인접 한 메모리 블록에 모든 보안 정보를 저장 하는 보안 설명자가입니다.  
  
##  <a name="get"></a>CPrivateObjectSecurityDesc::Get  
 개인 개체의 보안 설명자에서 정보를 검색 하려면이 메서드를 호출 합니다.  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `si`  
 검색할 보안 설명자의 부분을 나타내는 비트 플래그 집합입니다. 이 값의 조합일 수는 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) 비트 플래그입니다.  
  
 `pResult`  
 에 대 한 포인터는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 지정 된 보안 설명자에서 요청 된 정보의 복사본을 받는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 보안 설명자는 구조 및 보안 개체에 대 한 보안 정보를 포함 하는 연결 된 데이터.  
  
##  <a name="operator_eq"></a>CPrivateObjectSecurityDesc::operator =  
 대입 연산자입니다.  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `CPrivateObjectSecurityDesc` 현재 개체에 할당 하는 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CPrivateObjectSecurityDesc` 개체입니다.  
  
##  <a name="set"></a>CPrivateObjectSecurityDesc::Set  
 전용 개체의 보안 설명자를 수정 하려면이 메서드를 호출 합니다.  
  
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
 집합을 설정 하는 보안 설명자의 부분을 나타내는 비트 플래그입니다. 이 값의 조합일 수는 [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) 비트 플래그입니다.  
  
 *수정*  
 에 대 한 포인터는 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) 개체입니다. 이 보안 설명자의 부분으로 표시 된 `si` 매개 변수 개체의 보안 설명자에 적용 됩니다.  
  
 `GenericMapping`  
 에 대 한 포인터는 [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) 개체에 대 한 특정 권한을 갖도록 각 제네릭 오른쪽에서 매핑을 지정 하는 구조입니다.  
  
 `Token`  
 에 대 한 참조는 [CAccessToken](../../atl/reference/caccesstoken-class.md) 개체를 만든 대신 클라이언트 프로세스에 대 한 개체입니다.  
  
 `AutoInheritFlags`  
 액세스 제어 항목 (Ace)에서 상속 되는 방식을 제어 하는 비트 플래그 집합 `pParent`합니다. 참조 [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) 대 한 자세한 내용은 합니다.  
  
### <a name="return-value"></a>반환 값  
 성공하면 true를 반환하고, 실패하면 false를 반환합니다.  
  
### <a name="remarks"></a>주의  
 개체의 개체 형식 GUID를 지정할 수 또는 Windows 2000을 실행 하는 시스템에서 사용할 수 있고 이상만 Ace 상속 되는 방식을 제어 하는 두 번째 방법입니다.  
  
## <a name="see-also"></a>참고 항목  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc 클래스](../../atl/reference/csecuritydesc-class.md)

