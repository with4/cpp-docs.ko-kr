---
title: "CFixedStringT 클래스 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
dev_langs:
- C++
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: f357a70a728b388c3b5d3d26ac4efd0d4c84434a
ms.lasthandoff: 02/24/2017

---
# <a name="cfixedstringt-class"></a>CFixedStringT 클래스
이 클래스는 고정된 문자 버퍼와 string 개체를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>매개 변수  
 `StringType`  
 고정된 문자열 개체에 대 한 기본 클래스로 사용 하 고 하나일 수 있습니다 `CStringT`-기반 형식입니다. 몇 가지 예로 `CString`, `CStringA`, 및 `CStringW`합니다.  
  
 *t_nChars*  
 버퍼에 저장 된 문자 수입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](#cfixedstringt)|문자열 개체에 대 한 생성자입니다.|  
  
### <a name="public-operators"></a>Public 연산자  
  
|이름|설명|  
|----------|-----------------|  
|[CFixedStringT::operator =](#eq)|에 새 값을 할당 한 `CFixedStringT` 개체입니다.|  
  
## <a name="remarks"></a>주의  
 이 클래스는 기반으로 하는 사용자 지정 문자열 클래스의 예로 `CStringT`합니다. 매우 유사 하지만 두 클래스 구현에서 다릅니다. 주요 차이점 `CFixedStringT` 및 `CStringT` 됩니다.  
  
-   초기 문자 버퍼 개체의 일부로 할당 되 고 크기가 *t_nChars*합니다. 이 통해는 **CFixedString** 성능 향상을 위해 인접 한 메모리 청크를 차지 하는 개체입니다. 그러나 하는 경우의 콘텐츠는 `CFixedStringT` 개체 수가 늘어나면 *t_nChars*, 버퍼를 동적으로 할당 됩니다.  
  
-   에 대 한 문자 버퍼는 `CFixedStringT` 개체는 항상 동일한 길이 ( *t_nChars*). 에 대 한 버퍼 크기 제한은 `CStringT` 개체입니다.  
  
-   메모리 관리자에 대 한 `CFixedStringT` 를 공유할 수 있도록 사용자 지정 된 한 [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) 간에 두 개 이상의 개체 `CFixedStringT` objectsis 허용 되지 않습니다. `CStringT`개체에는 이러한 제한이 없습니다.  
  
 사용자 지정에 대 한 자세한 내용은 `CFixedStringT` string 개체의 메모리 관리는 일반적으로 참조 및 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** cstringt.h  
  
##  <a name="cfixedstringt"></a>CFixedStringT::CFixedStringT  
 `CFixedStringT` 개체를 생성합니다.  
  
```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT(const StringType& str);
CFixedStringT(const StringType::XCHAR* psz);
explicit CFixedStringT(const StringType::YCHAR* psz);
explicit CFixedStringT(const unsigned char* psz);
```  
  
### <a name="parameters"></a>매개 변수  
 `psz`  
 이로 복사 되는 null로 끝나는 문자열 `CFixedStringT` 개체입니다.  
  
 `str`  
 기존 `CFixedStringT` 이에 복사 될 개체 `CFixedStringT` 개체입니다.  
  
 `pStringMgr`  
 메모리 관리자에 대 한 포인터는 `CFixedStringT` 개체입니다. 대 한 자세한 내용은 `IAtlStringMgr` 및 메모리 관리에 대 한 `CFixedStringT`, 참조 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
### <a name="remarks"></a>주의  
 알고 있어야 새 할당 된 저장소에는 입력된 데이터를 복사 하는 생성자, 때문에 메모리 예외가 발생할 수 있습니다. 이러한 생성자 중 일부 역할을 할 변환 함수로 참고 합니다.  
  
##  <a name="operator__eq"></a>CFixedStringT::operator =  
 재초기화가 기존 `CFixedStringT` 새 데이터로 개체입니다.  
  
```
CFixedStringT<StringType, t_nChars>& operator=(
  const CFixedStringT<StringType, t_nChars>& str);
CFixedStringT<StringType, t_nChars>& operator=(const char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* psz);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* psz);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& str);
```  
  
### <a name="parameters"></a>매개 변수  
 `str`  
 이로 복사 되는 null로 끝나는 문자열 `CFixedStringT` 개체입니다.  
  
 `psz`  
 기존 `CFixedStringT` 이 개체로 복사할 `CFixedStringT` 개체입니다.  
  
### <a name="remarks"></a>주의  
 알고 있어야 해당 메모리 할당 연산자를 사용 하 여 결과 저장할 새 저장소가 할당 종종 때문에 때마다 예외가 발생할 수 있습니다 `CFixedStringT` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 클래스 공유](../../atl-mfc-shared/atl-mfc-shared-classes.md)





