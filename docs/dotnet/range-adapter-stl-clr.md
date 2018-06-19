---
title: range_adapter (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::range_adapter
dev_langs:
- C++
helpviewer_keywords:
- range_adapter class [STL/CLR]
ms.assetid: 3fbe2a65-1216-46a0-a182-422816b80cfb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 1a5b8a02856d7739867e3cf9f76f866a1e84efca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33162327"
---
# <a name="rangeadapter-stlclr"></a>range_adapter(STL/CLR)
여러 클래스 라이브러리 BCL (기본) 인터페이스를 구현 하는 데 사용 되는 반복기의 쌍을 래핑하는 템플릿 클래스입니다. BCL 컬렉션 하는 경우 STL/CLR 범위를 조작 하는 range_adapter를 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Iter>  
    ref class range_adapter  
        :   public  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<Value>,  
        System::Collections::Generic::ICollection<Value>  
    { ..... };  
```  
  
#### <a name="parameters"></a>매개 변수  
 iter  
 래핑된 반복기와 관련 된 형식입니다.  
  
## <a name="members"></a>멤버  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[range_adapter::range_adapter(STL/CLR)](../dotnet/range-adapter-range-adapter-stl-clr.md)|어댑터 개체를 생성 합니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[range_adapter::operator=(STL/CLR)](../dotnet/range-adapter-operator-assign-stl-clr.md)|저장 된 반복기 쌍을 바꿉니다.|  
  
## <a name="interfaces"></a>인터페이스  
  
|인터페이스|설명|  
|---------------|-----------------|  
|<xref:System.Collections.IEnumerable>|컬렉션의 요소를 반복 합니다.|  
|<xref:System.Collections.ICollection>|요소의 그룹을 유지 관리합니다.|  
|<xref:System.Collections.Generic.IEnumerable%601>|컬렉션에서 형식화 된 요소를 반복...|  
|<xref:System.Collections.Generic.ICollection%601>|형식화 된 요소의 그룹을 유지 관리합니다.|  
  
## <a name="remarks"></a>설명  
 range_adapter 차례로 요소의 시퀀스를 구분 하는 반복기 쌍을 저장 합니다. 개체는 요소, 순서 대로 반복할 수 있는 4 개의 BCL 인터페이스를 구현 합니다. 이 템플릿 클래스를 사용 하 여 STL/CLR 범위 BCL 컨테이너 매우 유사 하 게 조작할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/어댑터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [collection_adapter (STL/CLR)](../dotnet/collection-adapter-stl-clr.md)   
 [make_collection(STL/CLR)](../dotnet/make-collection-stl-clr.md)