---
title: "Platform::Collections::MapView 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
dev_langs: C++
helpviewer_keywords: MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
caps.latest.revision: "9"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db25b79476490ccc6bfc3f68370f30b7e8f2afac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsmapview-class"></a>Platform::Collections::MapView 클래스
읽기 전용 보기를 키/값 쌍의 컬렉션인 *맵*으로 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>>  
ref class MapView sealed;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `K`  
 키/값 쌍의 키 형식입니다.  
  
 `V`  
 키/값 쌍의 값 형식입니다.  
  
 `C`  
 두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std::less\<K >](../standard-library/less-struct.md)합니다.  
  
### <a name="remarks"></a>설명  
 MapView는의 구체적 c + + 구현에서 [Windows::Foundation::Collections::IMapView \<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262409) 응용 프로그램 이진 인터페이스 ABI ()를 통해 전달 되는 인터페이스입니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
### <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Mapview:: Mapview](#ctor)|MapView 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Mapview:: First](#first)|맵 뷰의 첫 번째 요소로 초기화하는 반복기를 반환합니다.|  
|[Mapview:: Haskey](#haskey)|현재 MapView에 지정한 키가 들어 있는지 여부를 확인합니다.|  
|[Mapview:: Lookup](#lookup)|현재 MapView 개체의 지정된 키에 있는 요소를 검색합니다.|  
|[Mapview:: Size](#size)|현재 MapView 개체의 요소 수를 반환합니다.|  
|[Mapview:: Split](#split)|원래 MapView 개체를 두 개의 MapView 개체로 분할합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `MapView`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  


## <a name="first"></a>Mapview:: First 메서드
맵 뷰의 첫 번째 요소를 지정하는 반복기를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>반환 값  
 맵 뷰의 첫 번째 요소를 지정하는 반복기입니다.  
  
### <a name="remarks"></a>설명  
 선언 된 변수에 반환 값을 할당 하는 First()에서 반환 된 반복기를 보유 하는 편리한 방법은 **자동** 형식 추론 키워드입니다. 예를 들어, `auto x = myMapView->First();`을 입력합니다.  
  


## <a name="haskey"></a>Mapview:: Haskey 메서드
현재 MapView에 지정한 키가 들어 있는지 여부를 확인합니다.  
  
### <a name="syntax"></a>구문  
  
```  
  
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 MapView 요소를 찾는 데 사용되는 키입니다. 유형의 `key` 형식 이름 *K*합니다.  
  
### <a name="return-value"></a>반환 값  
 키가 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  


##  <a name="lookup"></a>Mapview:: Lookup 메서드
K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 MapView에서 요소를 찾는 데 사용되는 키입니다. 유형의 `key` 형식 이름 *K*합니다.  
  
### <a name="return-value"></a>반환 값  
 `key`와 쌍을 이루는 값입니다. 반환 값의 형식이 typename *V*합니다.  
  


##  <a name="ctor"></a>Mapview:: Mapview 생성자
MapView 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
explicit MapView(const C& comp = C());  
  
explicit MapView(const ::std::map<K, V, C>& m);  
  
explicit MapView(std::map<K, V, C>&& m);  
  
template <typename InIt> MapView(  
    InIt first,  
    InIt last,  
    const C& comp = C());  
  
MapView(
    ::std::initializer_list<std::pair<const K, V>> il,  
    const C& comp = C());  
```  
  
### <a name="parameters"></a>매개 변수  
 `InIt`  
 현재 MapView의 형식 이름입니다.  
  
 `comp`  
 두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체입니다.  
  
 `m`  
 대 한 참조 또는 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) 에 `map Class` 현재 MapView를 초기화 하는 데 사용 되는 합니다.  
  
 `first`  
 현재 MapView를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.  
  
 `last`  
 현재 MapView를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.  
  
 il  
 A [std:: initializer_list < std:: pair\<K, V >>](../standard-library/initializer-list-class.md) 해당 요소가 MapView에 삽입 됩니다.  



##  <a name="size"></a>Mapview:: Size 메서드
현재 MapView 개체의 요소 수를 반환합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>반환 값  
 현재 MapView의 요소 수입니다.  
  


##  <a name="split"></a>Mapview:: Split 메서드
현재 MapView 개체를 두 개의 MapView 개체로 분할합니다. 이 메서드는 작동하지 않습니다.  
  
### <a name="syntax"></a>구문  
  
```  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K, V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K, V>^ * secondPartition);  
```  
  
### <a name="parameters"></a>매개 변수  
 `firstPartition`  
 원래 MapView 개체의 첫 번째 부분입니다.  
  
 `secondPartition`  
 원래 MapView 개체의 두 번째 부분입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 작동하지 않으며, 아무 작업도 수행하지 않습니다.  
    
## <a name="see-also"></a>참고 항목  
 [플랫폼 Namespace](platform-namespace-c-cx.md)