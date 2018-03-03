---
title: "CFixedStringT 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f66749272649fe230b31e770a175e0b94441b90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="cfixedstringt-class"></a>CFixedStringT 클래스
이 클래스는 문자열 개체가 고정된 문자 버퍼를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```  
  
#### <a name="parameters"></a>매개 변수  
 `StringType`  
 고정된 문자열 개체에 대 한 기본 클래스로 사용 되며 하나일 수 있습니다 `CStringT`-형식을 기반으로 합니다. 몇 가지 예로 `CString`, `CStringA`, 및 `CStringW`합니다.  
  
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
  
## <a name="remarks"></a>설명  
 이 클래스에 기반 하는 사용자 지정 문자열 클래스의 예는 `CStringT`합니다. 매우 유사 하지만 두 클래스는 구현에서 다 합니다. 주요 차이점 `CFixedStringT` 및 `CStringT` 됩니다.  
  
-   초기 문자 버퍼 개체의 일부로 할당 되 고 크기가 *t_nChars*합니다. 이 통해는 **CFixedString** 성능 향상을 위해 청크 인접 한 메모리를 차지 하는 개체입니다. 그러나 경우의 콘텐츠는 `CFixedStringT` 개체 크기가 다음을 초과 *t_nChars*, 버퍼를 동적으로 할당 됩니다.  
  
-   에 대 한 문자 버퍼는 `CFixedStringT` 개체는 항상 길이가 동일 ( *t_nChars*). 에 대 한 버퍼 크기 제한은 `CStringT` 개체입니다.  
  
-   메모리 관리자에 대 한 `CFixedStringT` 의 공유 되도록 사용자 지정 된는 [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) 둘 이상의 개체 `CFixedStringT` objectsis 허용 되지 않습니다. `CStringT`개체에는 이러한 제한이 없습니다.  
  
 사용자 지정에 대 한 자세한 내용은 `CFixedStringT` string 개체의 메모리 관리는 일반적으로 참조 하 고 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
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
 이 복사 되는 null로 끝나는 문자열 `CFixedStringT` 개체입니다.  
  
 `str`  
 기존 `CFixedStringT` 이 복사 되는 개체 `CFixedStringT` 개체입니다.  
  
 `pStringMgr`  
 메모리 관리자에 대 한 포인터는 `CFixedStringT` 개체입니다. 대 한 자세한 내용은 `IAtlStringMgr` 및 메모리 관리에 대 한 `CFixedStringT`, 참조 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.  
  
### <a name="remarks"></a>설명  
 알고 있어야 새 할당 된 저장소에 입력된 데이터를 복사 하는 생성자를 때문에 메모리 예외가 발생할 수 있습니다. 이러한 생성자 중 일부는 역할 변환 함수를 참고 합니다.  
  
##  <a name="operator__eq"></a>CFixedStringT::operator =  
 기존 다시 초기화 `CFixedStringT` 새 데이터로 개체입니다.  
  
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
 이 복사 되는 null로 끝나는 문자열 `CFixedStringT` 개체입니다.  
  
 `psz`  
 기존 `CFixedStringT` 이 복사할 `CFixedStringT` 개체입니다.  
  
### <a name="remarks"></a>설명  
 알아야 할 메모리 할당 연산자를 사용 하 여 결과 보유 하는 새 저장소를 할당 종종 때문에 때마다 예외가 발생할 수 있습니다는 `CFixedStringT` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)




