---
title: collection_adapter (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::collection_adapter
dev_langs:
- C++
helpviewer_keywords:
- collection_adapter class [STL/CLR]
ms.assetid: 31964058-1f50-48bf-82c2-b0b3cc8a7887
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4a1a03dd6ecc52cd3921428e681fe5affa11d275
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="collectionadapter-stlclr"></a>collection_adapter(STL/CLR)
STL/CLR 컨테이너로 사용 하기 위해.NET 컬렉션을 래핑합니다. A `collection_adapter` 간단한 STL/CLR 컨테이너 개체를 설명 하는 템플릿 클래스입니다. 클래스 라이브러리 BCL (기본) 인터페이스를 래핑하고 제어 되는 시퀀스를 조작 하는 데 사용 하는 반복기 쌍을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
template<typename Coll>  
    ref class collection_adapter;  
  
template<>  
    ref class collection_adapter<  
        System::Collections::ICollection>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IEnumerable>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IList>;  
template<>  
    ref class collection_adapter<  
        System::Collections::IDictionary>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::ICollection<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IEnumerable<Value>>;  
template<typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IList<Value>>;  
template<typename Key,  
    typename Value>  
    ref class collection_adapter<  
        System::Collections::Generic::IDictionary<Key, Value>>;  
```  
  
#### <a name="parameters"></a>매개 변수  
 C o l l  
 래핑된 컬렉션의 형식입니다.  
  
## <a name="specializations"></a>특수화  
  
|특수화|설명|  
|--------------------|-----------------|  
|IEnumerable|요소를 통해 순서입니다.|  
|ICollection|요소의 그룹을 유지 관리합니다.|  
|IList|요소의 정렬된 된 그룹을 유지 관리합니다.|  
|IDictionary|{키, 값} 집합 유지 관리 쌍입니다.|  
|IEnumerable\<값 >|형식화 된 요소를 통해 순서입니다.|  
|ICollection\<값 >|형식화 된 요소의 그룹을 유지 관리합니다.|  
|IList\<값 >|형식화 된 요소의 정렬된 된 그룹을 유지 관리합니다.|  
|IDictionary\<값 >|형식화 된 {키의 값을 (를) 집합을 유지 관리 쌍입니다.|  
  
## <a name="members"></a>멤버  
  
|형식 정의|설명|  
|---------------------|-----------------|  
|[collection_adapter::difference_type(STL/CLR)](../dotnet/collection-adapter-difference-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[collection_adapter::iterator(STL/CLR)](../dotnet/collection-adapter-iterator-stl-clr.md)|제어되는 시퀀스에 대한 반복기의 형식입니다.|  
|[collection_adapter::key_type(STL/CLR)](../dotnet/collection-adapter-key-type-stl-clr.md)|사전 키의 형식입니다.|  
|[collection_adapter::mapped_type(STL/CLR)](../dotnet/collection-adapter-mapped-type-stl-clr.md)|사전 값의 형식입니다.|  
|[collection_adapter::reference(STL/CLR)](../dotnet/collection-adapter-reference-stl-clr.md)|요소에 대한 참조의 형식입니다.|  
|[collection_adapter::size_type(STL/CLR)](../dotnet/collection-adapter-size-type-stl-clr.md)|두 요소 사이의 부호가 있는 거리의 형식입니다.|  
|[collection_adapter::value_type(STL/CLR)](../dotnet/collection-adapter-value-type-stl-clr.md)|요소의 형식입니다.|  
  
|멤버 함수|설명|  
|---------------------|-----------------|  
|[collection_adapter::base(STL/CLR)](../dotnet/collection-adapter-base-stl-clr.md)|래핑된 BCL 인터페이스를 지정합니다.|  
|[collection_adapter::begin(STL/CLR)](../dotnet/collection-adapter-begin-stl-clr.md)|제어되는 시퀀스의 시작을 지정합니다.|  
|[collection_adapter::collection_adapter(STL/CLR)](../dotnet/collection-adapter-collection-adapter-stl-clr.md)|어댑터 개체를 생성 합니다.|  
|[collection_adapter::end(STL/CLR)](../dotnet/collection-adapter-end-stl-clr.md)|제어되는 시퀀스의 끝을 지정합니다.|  
|[collection_adapter::size(STL/CLR)](../dotnet/collection-adapter-size-stl-clr.md)|요소 수를 계산합니다.|  
|[collection_adapter::swap(STL/CLR)](../dotnet/collection-adapter-swap-stl-clr.md)|두 컨테이너의 내용을 바꿉니다.|  
  
|연산자|설명|  
|--------------|-----------------|  
|[collection_adapter::operator=(STL/CLR)](../dotnet/collection-adapter-operator-assign-stl-clr.md)|저장된 BCL 핸들을 대체합니다.|  
  
## <a name="remarks"></a>설명  
 이 템플릿 클래스를 사용 하 여 STL/CLR 컨테이너로 BCL 컨테이너를 조작 합니다. `collection_adapter` 차례로 요소의 시퀀스를 제어 하는 BCL 인터페이스에 대 한 핸들을 저장 합니다. A `collection_adapter` 개체 `X` 입력된 반복기의 쌍을 반환 `X.begin()` 및 `X.end()` 요소, 순서 대로 방문 하 여 사용 하는 합니다. 특수화의 일부도 작성할 수 `X.size()` 제어 된 시퀀스의 길이 확인 하 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** \<cliext/어댑터 >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>참고 항목  
 [range_adapter (STL/CLR)](../dotnet/range-adapter-stl-clr.md)   
 [make_collection(STL/CLR)](../dotnet/make-collection-stl-clr.md)