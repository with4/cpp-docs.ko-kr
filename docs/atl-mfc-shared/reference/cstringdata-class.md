---
title: "CStringData 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringData
dev_langs:
- C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b7dfebebbec7acc774fa2e63ab9fafed788f679a
ms.lasthandoff: 02/24/2017

---
# <a name="cstringdata-class"></a>CStringData 클래스
이 클래스는 문자열 개체의 데이터를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
struct CStringData
```  
  
## <a name="members"></a>멤버  
  
### <a name="methods"></a>메서드  
  
|||  
|-|-|  
|[AddRef](#addref)|문자열 데이터 개체의 참조 횟수를 증가 시킵니다.|  
|[data](#data)|String 개체의 문자 데이터를 검색합니다.|  
|[IsLocked](#islocked)|연결 된 문자열 개체의 버퍼 잠겨 있는지 확인 합니다.|  
|[IsShared](#isshared)|연결 된 문자열 개체의 버퍼는 현재 공유 하는 경우를 결정 합니다.|  
|[잠금](#lock)|연결 된 문자열 개체의 버퍼를 잠급니다.|  
|[릴리스](#release)|지정 된 문자열 개체를 해제합니다.|  
|[잠금 해제](#unlock)|연결 된 문자열 개체의 버퍼를 잠금 해제합니다.|  
  
### <a name="data-members"></a>데이터 멤버  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|에 할당 된 데이터의 길이 `XCHAR`s (제외, 종료 null)|  
|[nDataLength](#ndatalength)|현재 사용 되는 데이터의 길이 `XCHAR`s (제외, 종료 null)|  
|[nRefs](#nrefs)|개체의 현재 참조 횟수를 지정 합니다.|  
|[pStringMgr](#pstringmgr)|이 문자열 개체의 문자열 관리자에 대 한 포인터입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 사용자 지정 문자열 관리자를 구현 하는 개발자만 사용 해야 합니다. 사용자 지정 문자열 관리자에 대 한 자세한 내용은 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 이 클래스는 다양 한 종류의 정보와 같은 높은 문자열 개체와 연결 된 데이터를 캡슐화 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), 또는 [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) 개체입니다. 해당 연결에 대 한 포인터를 포함 하는 모든 높은 문자열 개체 `CStringData` 개체를 여러 string 개체에 같은 문자열 데이터 개체를 가리키도록 합니다. 이 관계의 참조 횟수가 표시 됩니다 ( `nRefs`)의 `CStringData` 개체입니다.  
  
> [!NOTE]
>  경우에 따라 문자열 형식 (예: **CFixedString**) 둘 이상의 높은 문자열 개체와 문자열 데이터 개체를 공유 하지 것입니다. 이 대 한 자세한 내용은 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
 이 데이터는 구성 됩니다.  
  
-   메모리 관리자 (형식의 [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md))는 문자열입니다.  
  
-   현재 길이 ( [nDataLength](#ndatalength))는 문자열입니다.  
  
-   할당 된 길이 ( [nAllocLength](#nalloclength))는 문자열입니다. 성능상의 이유로이 다를 수에서 현재 문자열 길이  
  
-   현재 참조 수가 ( [nRefs](#nrefs))의 `CStringData` 개체입니다. 이 값은 문자열 개체의 수가 동일를 공유 하는 결정 하는 데 사용 `CStringData` 개체입니다.  
  
-   실제 문자 버퍼 ( [데이터](#data))는 문자열입니다.  
  
    > [!NOTE]
    >  String 개체의 실제 문자 버퍼 문자열 관리자가 할당 되 고에 추가 되는 `CStringData` 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsimpstr.h  
  
##  <a name="a-nameaddrefa--cstringdataaddref"></a><a name="addref"></a>CStringData::AddRef  
 String 개체의 참조 횟수를 증가 시킵니다.  
  
```
void AddRef() throw();
```  
  
### <a name="remarks"></a>주의  
 String 개체의 참조 횟수를 증가 시킵니다.  
  
> [!NOTE]
>  문자열 버퍼 잠겨 음수 표시 되므로 음수 참조 횟수를 포함 된 문자열에서이 메서드를 호출 하지 마십시오.  
  
##  <a name="a-namedataa--cstringdatadata"></a><a name="data"></a>CStringData::data  
 String 개체의 문자 버퍼에 대 한 포인터를 반환합니다.  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>반환 값  
 String 개체의 문자 버퍼에 대 한 포인터입니다.  
  
### <a name="remarks"></a>주의  
 연결 된 문자열 개체의 현재 문자 버퍼를 반환 하려면이 함수를 호출 합니다.  
  
> [!NOTE]
>  이 버퍼에서 할당 되지 않은 `CStringData` 개체 있지만 필요할 때 문자열 관리자가 있습니다. 할당 된 버퍼 문자열 데이터 개체에 추가 됩니다.  
  
##  <a name="a-nameislockeda--cstringdataislocked"></a><a name="islocked"></a>CStringData::IsLocked  
 문자 버퍼 잠겨 있는지 확인 합니다.  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 버퍼가 잠긴 하 고, 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>주의  
 현재 string 개체의 문자 버퍼 잠겨 있는지 확인 하려면이 함수를 호출 합니다.  
  
##  <a name="a-nameisshareda--cstringdataisshared"></a><a name="isshared"></a>CStringData::IsShared  
 문자 버퍼는 공유 하는 경우를 결정 합니다.  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>반환 값  
 반환 **true** 버퍼가 공유 하 고, 그렇지 않으면 **false**합니다.  
  
### <a name="remarks"></a>주의  
 문자열 데이터 개체의 문자 버퍼 현재 여러 string 개체 간에 공유 되는지 확인 하려면이 함수를 호출 합니다.  
  
##  <a name="a-namelocka--cstringdatalock"></a><a name="lock"></a>CStringData::Lock  
 연결 된 문자열 개체의 문자 버퍼를 잠급니다.  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>주의  
 이 함수는 문자열 데이터 개체의 문자 버퍼를 잠글 수를 호출 합니다. 잠금 및 잠금 해제는 개발자가 문자 버퍼에 대 한 직접 액세스 해야 할 경우에 사용 됩니다. 증명 된 잠금의 좋은 예는 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 의 메서드 `CSimpleStringT`합니다.  
  
> [!NOTE]
>  문자 버퍼 버퍼 높은 string 개체 간에 공유 되지 않는 경우에 잠글 수 있습니다.  
  
##  <a name="a-namenalloclengtha--cstringdatanalloclength"></a><a name="nalloclength"></a>CStringData::nAllocLength  
 문자 할당 된 버퍼의 길이입니다.  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>주의  
 할당 된 데이터 버퍼의 길이 저장 `XCHAR`s (종료 null) 포함 되지 않습니다.  
  
##  <a name="a-namendatalengtha--cstringdatandatalength"></a><a name="ndatalength"></a>CStringData::nDataLength  
 String 개체의 현재 길이입니다.  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>주의  
 현재 사용 되는 데이터의 길이 저장 `XCHAR`s (종료 null) 포함 되지 않습니다.  
  
##  <a name="a-namenrefsa--cstringdatanrefs"></a><a name="nrefs"></a>CStringData::nRefs  
 문자열 데이터 개체의 참조 횟수입니다.  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>주의  
 문자열 데이터 개체의 참조 횟수를 저장합니다. 이 수는 문자열 데이터 개체와 연관 된 높은 string 개체의 수를 나타냅니다. 음수 값을 현재 문자열 데이터 개체가 잠겨 있는지 나타냅니다.  
  
##  <a name="a-namepstringmgra--cstringdatapstringmgr"></a><a name="pstringmgr"></a>CStringData::pStringMgr  
 연결 된 문자열 개체의 메모리 관리자입니다.  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>주의  
 연결 된 문자열 개체에 대 한 메모리 관리자를 저장합니다. 메모리 관리자와 문자열에 대 한 자세한 내용은 참조 하십시오. [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
##  <a name="a-namereleasea--cstringdatarelease"></a><a name="release"></a>CStringData::Release  
 문자열 데이터 개체의 참조 횟수를 감소 시킵니다.  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>주의  
 참조 횟수를 감소 시키기 위해이 함수를 호출 해제는 `CStringData` 참조 횟수가&0;에 도달한 경우를 구성 합니다. 이 문자열 개체가 삭제 되 고 따라서 더 이상 필요 없는 문자열 데이터 개체를 참조 하는 경우 일반적으로 수행 됩니다.  
  
 예를 들어, 다음 코드는을 호출 `CStringData::Release` 와 연결 된 문자열 데이터 개체에 대 한 `str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&104;](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="a-nameunlocka--cstringdataunlock"></a><a name="unlock"></a>CStringData::Unlock  
 연결 된 문자열 개체의 문자 버퍼를 잠금 해제합니다.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>주의  
 문자열 데이터 개체의 문자 버퍼를 잠금 해제 하려면이 함수를 호출 합니다. 버퍼 잠금이 해제 되 면 공유 가능 및 참조 카운트할 수 있습니다.  
  
> [!NOTE]
>  호출할 때마다 `Lock` 해당 호출을 통해 일치 해야 `Unlock`합니다.  
  
 개발자는 문자열 데이터를 공유 하지 확인 해야 하는 경우 잠금 및 잠금 해제 사용 됩니다. 증명 된 잠금의 좋은 예는 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) 및 [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) 의 메서드 `CSimpleStringT`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 클래스 공유](../../atl-mfc-shared/atl-mfc-shared-classes.md)



