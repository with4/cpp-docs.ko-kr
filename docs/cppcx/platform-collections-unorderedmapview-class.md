---
title: "Platform::Collections::UnorderedMapView 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: "5"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c172246bc0e8fd7acb1661a9547fee3bf6c24421
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView 클래스
읽기 전용 보기를 키/값 쌍의 컬렉션인 *맵*으로 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>>  
ref class UnorderedMapView sealed;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `K`  
 키/값 쌍의 키 형식입니다.  
  
 `V`  
 키/값 쌍의 값 형식입니다.  
  
 `C`  
 같은지 확인하기 위해 두 키 값을 비교할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:: equal_to\<K >](../standard-library/equal-to-struct.md)  
  
### <a name="remarks"></a>설명  
 UnorderedMapView는의 구체적 c + + 구현에서 [Windows::Foundation::Collections::IMapView\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262409) 응용 프로그램 이진 인터페이스 ABI ()를 통해 전달 되는 인터페이스입니다. 자세한 내용은 [컬렉션(C++/CX)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
### <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Unorderedmapview:: Unorderedmapview](#ctor)|UnorderedMapView 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Unorderedmapview:: First](#first)|맵 뷰의 첫 번째 요소로 초기화하는 반복기를 반환합니다.|  
|[Unorderedmapview:: Haskey](#haskey)|현재 UnorderedMapView에 지정한 키가 들어 있는지 여부를 확인합니다.|  
|[Unorderedmapview:: Lookup](#lookup)|현재 UnorderedMapView 개체의 지정된 키에 있는 요소를 검색합니다.|  
|[Unorderedmapview:: Size](#size)|현재 UnorderedMapView 개체의 요소 수를 반환합니다.|  
|[Unorderedmapview:: Split](#split)|원래 UnorderedMapView 개체를 두 개의 UnorderedMapView 개체로 분할합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `UnorderedMapView`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  

## <a name="first"></a>  UnorderedMapView::First 메서드
첫 번째 지정 하는 반복기를 반환 [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) unordered map의 요소입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp   
virtual Windows::Foundation::Collections::IIterator<  
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
    First();  
```  
  
### <a name="return-value"></a>반환 값  
 맵 뷰의 첫 번째 요소를 지정하는 반복기입니다.  
  
### <a name="remarks"></a>설명  
 선언 된 변수에 반환 값을 할당 하는 First()에서 반환 된 반복기를 보유 하는 편리한 방법은 **자동** 형식 추론 키워드입니다. 예를 들어, `auto x = myMapView->First();`을 입력합니다.  
  


## <a name="haskey"></a>  UnorderedMapView::HasKey 메서드
현재 UnorderedMap에 지정한 키가 들어 있는지 여부를 확인합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 요소를 찾는 데 사용되는 키입니다. 유형의 `key` 형식 이름 *K*합니다.  
  
### <a name="return-value"></a>반환 값  
 키가 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  


## <a name="lookup"></a>  UnorderedMapView::Lookup 메서드
K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 UnorderedMapView에서 요소를 찾는 데 사용되는 키입니다. 유형의 `key` 형식 이름 *K*합니다.  
  
### <a name="return-value"></a>반환 값  
 `key`와 쌍을 이루는 값입니다. 반환 값의 형식이 typename *V*합니다.  
  


## <a name="size"></a>  UnorderedMapView::Size 메서드
개수를 반환 [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) UnorderedMapView에 있는 요소입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>반환 값  
 UnorderedMapView의 요소 수입니다.  
  


## <a name="split"></a>  UnorderedMapView::Split 메서드
현재 UnorderedMapView 개체를 두 개의 UnorderedMapView 개체로 나눕니다. 이 메서드는 작동하지 않습니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * secondPartition);  
```  
  
### <a name="parameters"></a>매개 변수  
 `firstPartition`  
 원래 UnorderedMapView 개체의 첫 번째 부분입니다.  
  
 `secondPartition`  
 원래 UnorderedMapView 개체의 두 번째 부분입니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 작동하지 않으며, 아무 작업도 수행하지 않습니다.  
  


## <a name="ctor"></a>  UnorderedMapView::UnorderedMapView 생성자
UnorderedMapView 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
UnorderedMapView();    
explicit UnorderedMapView(size_t n);   
UnorderedMapView(size_t n, const H& h);   
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m);  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m);  
  
template <typename InIt> UnorderedMapView(InIt first, InIt last );  
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p );  
  
UnorderedMapView(std::initializer_list<std::pair<const K, V>);  
  
UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n   
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h);  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p );  
```  
  
### <a name="parameters"></a>매개 변수  
 n  
 공간을 미리 할당할 요소의 수입니다.  
  
 `InIt`  
 UnorderedMapView의 형식 이름입니다.  
  
 `H`  
 키에 해시 값을 사용할 수 있는 함수 개체입니다. 기본적으로 [std:: hash\<K >](http://msdn.microsoft.com/en-us/54f67435-af9d-4217-a29d-fa4d2491a104) 형식에는 `std::hash` 지원 합니다.  
  
 `P`  
 같은지 확인하기 위해 두 키를 비교할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:: equal_to\<K >](../standard-library/equal-to-struct.md)합니다.  
  
 `m`  
 대 한 참조 또는 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) 에 [std:: unordered_map](../standard-library/unordered-map-class.md) UnorderedMapView를 초기화 하는 데 사용 되는 합니다.  
  
 `first`  
 UnorderedMapView를 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.  
  
 `last`  
 UnorderedMapView를 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.  
   
## <a name="see-also"></a>참고 항목  
 [Platform:: collections Namespace](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)