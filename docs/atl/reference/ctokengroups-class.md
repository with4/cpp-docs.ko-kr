---
title: "CTokenGroups 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CTokenGroups
- ATLSECURITY/ATL::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::CTokenGroups
- ATLSECURITY/ATL::CTokenGroups::Add
- ATLSECURITY/ATL::CTokenGroups::Delete
- ATLSECURITY/ATL::CTokenGroups::DeleteAll
- ATLSECURITY/ATL::CTokenGroups::GetCount
- ATLSECURITY/ATL::CTokenGroups::GetLength
- ATLSECURITY/ATL::CTokenGroups::GetPTOKEN_GROUPS
- ATLSECURITY/ATL::CTokenGroups::GetSidsAndAttributes
- ATLSECURITY/ATL::CTokenGroups::LookupSid
dev_langs:
- C++
helpviewer_keywords:
- CTokenGroups class
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 41b93e1c0a2e55013e280023a7f47610d38ddc10
ms.contentlocale: ko-kr
ms.lasthandoff: 02/24/2017

---
# <a name="ctokengroups-class"></a>CTokenGroups 클래스
이 클래스는에 대 한 래퍼는 **TOKEN_GROUPS** 구조입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CTokenGroups
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CTokenGroups::CTokenGroups](#ctokengroups)|생성자입니다.|  
|[CTokenGroups:: ~ CTokenGroups](#dtor)|소멸자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[CTokenGroups::Add](#add)|추가 `CSid` 기존의 또는 **TOKEN_GROUPS** 구조체는 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::Delete](#delete)|삭제는 `CSid` 및 이와 관련 된 특성에서는 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::DeleteAll](#deleteall)|모든 삭제 `CSid` 개체 및 이와 연관 된 특성에서는 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::GetCount](#getcount)|개수를 반환 `CSid` 개체와 연결 된 특성에 포함 된는 **CTokenGroups** 개체입니다.|  
|[CTokenGroups::GetLength](#getlength)|크기를 반환 하는 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::GetPTOKEN_GROUPS](#getptoken_groups)|검색에 대 한 포인터는 **TOKEN_GROUPS** 구조입니다.|  
|[CTokenGroups::GetSidsAndAttributes](#getsidsandattributes)|검색 된 `CSid` 개체와 특성에 속한는 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::LookupSid](#lookupsid)|와 연결 된 특성을 검색 한 `CSid` 개체입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CTokenGroups::operator const TOKEN_GROUPS *](#operator_const_token_groups__star)|캐스트는 `CTokenGroups` 개체에 대 한 포인터는 **TOKEN_GROUPS** 구조입니다.|  
|[CTokenGroups::operator =](#operator_eq)|대입 연산자입니다.|  
  
## <a name="remarks"></a>주의  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 는 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 하는 개체입니다.  
  
 **CTokenGroups** 클래스에 대 한 래퍼는는 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) 그룹 보안 식별자 (Sid) 액세스 토큰에 대 한 정보가 포함 된 구조입니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="add"></a>CTokenGroups::Add  
 추가 `CSid` 기존의 또는 **TOKEN_GROUPS** 구조체는 `CTokenGroups` 개체입니다.  
  
```
void Add(const CSid& rSid, DWORD dwAttributes) throw(... );  
void Add(const TOKEN_GROUPS& rTokenGroups) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 A [CSid](../../atl/reference/csid-class.md) 개체입니다.  
  
 `dwAttributes`  
 와 연결할 특성은 `CSid` 개체입니다.  
  
 *rTokenGroups*  
 A [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) 구조입니다.  
  
### <a name="remarks"></a>주의  
 이러한 방법을 하나 이상 추가 `CSid` 개체 및 이와 연관 된 특성에는 `CTokenGroups` 개체입니다.  
  
##  <a name="ctokengroups"></a>CTokenGroups::CTokenGroups  
 생성자입니다.  
  
```
CTokenGroups() throw();
CTokenGroups(const CTokenGroups& rhs) throw(... );  
CTokenGroups(const TOKEN_GROUPS& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `CTokenGroups` 개체 또는 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) 구조를 생성 하는 `CTokenGroups` 개체입니다.  
  
### <a name="remarks"></a>주의  
 `CTokenGroups` 를 사용 하 여 개체를 만들 수 있습니다는 **TOKEN_GROUPS** 구조 또는 이전에 정의 된 `CTokenGroups` 개체입니다.  
  
##  <a name="dtor"></a>CTokenGroups:: ~ CTokenGroups  
 소멸자입니다.  
  
```
virtual ~CTokenGroups() throw();
```  
  
### <a name="remarks"></a>주의  
 소멸자는 할당 된 모든 리소스를 해제합니다.  
  
##  <a name="delete"></a>CTokenGroups::Delete  
 삭제는 `CSid` 및 이와 관련 된 특성에서는 `CTokenGroups` 개체입니다.  
  
```
bool Delete(const CSid& rSid) throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md) 개체는에 대 한 SID (보안 식별자) 및 특성 제거 해야 합니다.  
  
### <a name="return-value"></a>반환 값  
 경우 true를 반환 된 `CSid` 제거 되 면 false 그렇지 않은 경우.  
  
##  <a name="deleteall"></a>CTokenGroups::DeleteAll  
 모든 삭제 `CSid` 개체 및 이와 연관 된 특성에서는 `CTokenGroups` 개체입니다.  
  
```
void DeleteAll() throw();
```  
  
##  <a name="getcount"></a>CTokenGroups::GetCount  
 개수를 반환 `CSid` 에 포함 된 개체 `CTokenGroups`합니다.  
  
```
UINT GetCount() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 개수를 반환 [CSid](../../atl/reference/csid-class.md) 개체와 연관 된 특성에 포함 된는 `CTokenGroups` 개체입니다.  
  
##  <a name="getlength"></a>CTokenGroups::GetLength  
 크기를 반환 하는 **CTokenGroup** 개체입니다.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="remarks"></a>주의  
 총 크기를 반환 하는 **CTokenGroup** 개체를 바이트 단위로 합니다.  
  
##  <a name="getptoken_groups"></a>CTokenGroups::GetPTOKEN_GROUPS  
 검색에 대 한 포인터는 **TOKEN_GROUPS** 구조입니다.  
  
```
const TOKEN_GROUPS* GetPTOKEN_GROUPS() const throw(...);
```  
  
### <a name="return-value"></a>반환 값  
 검색에 대 한 포인터는 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) 구조에 속하는 `CTokenGroups` 액세스 토큰 개체입니다.  
  
##  <a name="getsidsandattributes"></a>CTokenGroups::GetSidsAndAttributes  
 검색은 `CSid` 개체 및 (선택적 요소)에 속한 특성은 `CTokenGroups` 개체입니다.  
  
```
void GetSidsAndAttributes(
    CSid::CSidArray* pSids,
    CAtlArray<DWORD>* pAttributes = NULL) const throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `pSids`  
 배열에 대 한 포인터 [CSid](../../atl/reference/csid-class.md) 개체입니다.  
  
 `pAttributes`  
 Dword의 배열에 대 한 포인터입니다. 이 매개 변수가 생략 하거나 NULL 인 경우에 특성 검색 되지 됩니다.  
  
### <a name="remarks"></a>주의  
 이 메서드는 모두 열거 합니다는 `CSid` 에 포함 된 개체는 `CTokenGroups` 개체 및 배열 개체에 하 고 (선택 사항) 특성 플래그를 배치 합니다.  
  
##  <a name="lookupsid"></a>CTokenGroups::LookupSid  
 와 연결 된 특성을 검색 한 `CSid` 개체입니다.  
  
```
bool LookupSid(  
    const CSid& rSid,
    DWORD* pdwAttributes = NULL) const throw();
```  
  
### <a name="parameters"></a>매개 변수  
 `rSid`  
 [CSid](../../atl/reference/csid-class.md) 개체입니다.  
  
 `pdwAttributes`  
 수락 하는 DWORD에 대 한 포인터는 `CSid` 개체의 특성입니다. 지정 하지 않거나 NULL 특성 검색 되지 않습니다.  
  
### <a name="return-value"></a>반환 값  
 경우 true를 반환 된 `CSid` 발견 되 면 false 그렇지 않은 경우.  
  
### <a name="remarks"></a>주의  
 설정 `pdwAttributes` 를 NULL 있는지 확인 하는 방법을 제공 된 `CSid` 특성에 액세스 하지 않고 있습니다. Note Windows 2000에서 잘못 된 결과가 발생할 수 있습니다 액세스 권한을 확인 하려면이 메서드를 사용 하지 해야 합니다. 응용 프로그램을 대신 사용 해야는 [CAccessToken::CheckTokenMembership](../../atl/reference/caccesstoken-class.md#checktokenmembership) 메서드.  
  
##  <a name="operator_eq"></a>CTokenGroups::operator =  
 대입 연산자입니다.  
  
```
CTokenGroups& operator= (const TOKEN_GROUPS& rhs) throw(...);  
CTokenGroups& operator= (const CTokenGroups& rhs) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rhs`  
 `CTokenGroups` 개체 또는 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) 구조에 할당 하는 `CTokenGroups` 개체입니다.  
  
### <a name="return-value"></a>반환 값  
 업데이트 된 반환 `CTokenGroups` 개체입니다.  
  
##  <a name="operator_const_token_groups__star"></a>CTokenGroups::operator const TOKEN_GROUPS *  
 에 대 한 포인터 값에 캐스트는 **TOKEN_GROUPS** 구조입니다.  
  
```  
operator const TOKEN_GROUPS *() const throw(...);
```  
  
### <a name="remarks"></a>주의  
 에 대 한 포인터 값에 캐스트는 [TOKEN_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) 구조입니다.  
  
## <a name="see-also"></a>참고 항목  
 [보안 샘플](../../visual-cpp-samples.md)   
 [CSid 클래스](../../atl/reference/csid-class.md)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)

