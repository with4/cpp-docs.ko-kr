---
title: "Platform::Collections::UnorderedMap 클래스 | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: f926b400e1cfa2b7b4649efcd0bac73de1faa062
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap 클래스
키-값 쌍의 컬렉션인 순서가 지정되지 않은 *맵*을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = std::equal_to<K>  
>  
ref class Map sealed;  
```  
  
#### <a name="parameters"></a>매개 변수  
 `K`  
 키/값 쌍의 키 형식입니다.  
  
 `V`  
 키/값 쌍의 값 형식입니다.  
  
 `C`  
 두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본적으로 [std:: equal_to\<K >](../standard-library/equal-to-struct.md)합니다.  
  
### <a name="remarks"></a>설명  
 허용되는 형식은 다음과 같습니다.  
  
-   정수  
  
-   인터페이스 클래스 ^  
  
-   public ref 클래스 ^  
  
-   value struct  
  
-   public enum 클래스  
  
 UnorderedMap은 기본적으로 대 한 래퍼 [std:: unordered_map](../standard-library/unordered-map-class.md) 지 원하는 Windows 런타임 형식의 저장 합니다. 구체적인 구현을 [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) 및 [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) 공용 간에 전달 되는 형식을 Windows 런타임 인터페이스입니다. 공용 반환 값 또는 매개 변수에서 Platform::Collections::UnorderedMap 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수나 반환 값 형식을 [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408)으로 변경하여 오류를 수정할 수 있습니다.  
  
 자세한 내용은 참조 [컬렉션](../cppcx/collections-c-cx.md)합니다.  
  
### <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[Unorderedmap:: Unorderedmap](#ctor)|Map 클래스의 새 인스턴스를 초기화합니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Unorderedmap:: Clear](#clear)|현재 Map 개체에서 모든 키/값 쌍을 제거합니다.|  
|[Unorderedmap:: First](#first)|맵의 첫 번째 요소를 지정하는 반복기를 반환합니다.|  
|[Unorderedmap:: Getview](#getview)|현재 Map의 읽기 전용 뷰, 즉 Platform::Collections::UnorderedMapView 클래스를 반환합니다.|  
|[Unorderedmap:: Haskey](#haskey)|현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.|  
|[Unorderedmap:: Insert](#insert)|지정한 키/값 쌍을 현재 Map 개체에 추가합니다.|  
|[Unorderedmap:: Lookup](#lookup)|현재 Map 개체의 지정된 키에 있는 요소를 검색합니다.|  
|[Unorderedmap:: Remove](#remove)|지정한 키/값 쌍을 현재 Map 개체에서 삭제합니다.|  
|[Unorderedmap:: Size](#size)|현재 Map 개체의 요소 수를 반환합니다.|  
  
### <a name="events"></a>이벤트  
  
|||  
|-|-|  
|이름|설명|  
|[Map:: mapchanged](#mapchanged)`event`|Map이 변경될 때 발생합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `UnorderedMap`  
  
### <a name="requirements"></a>요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  

## <a name="clear"></a>Unorderedmap:: Clear 메서드
현재 UnorderedMap 개체에서 모든 키-값 쌍을 제거합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
virtual void Clear();   
```  
  


## <a name="first"></a>Unorderedmap:: First 메서드
첫 번째 지정 하는 반복기를 반환 [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) unordered map의 요소입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>반환 값  
 맵의 첫 번째 요소를 지정하는 반복기입니다.  
  
### <a name="remarks"></a>설명  
 선언 된 변수에 반환 값을 할당 하는 First()에서 반환 된 반복기를 보유 하는 편리한 방법은 **자동** 형식 추론 키워드입니다. 예를 들어, `auto x = myUnorderedMap->First();`을 입력합니다.  
  


## <a name="getview"></a>Unorderedmap:: Getview 메서드
현재 UnorderedMap의 읽기 전용 보기를 반환합니다. 즉, 한 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md) 구현 하는 [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) 인터페이스입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
Windows::Foundation::Collections::IMapView<K, V>^   
   GetView();  
```  
  
### <a name="return-value"></a>반환 값  
 `UnorderedMapView` 개체입니다.  
  


## <a name="haskey"></a>Unorderedmap:: Haskey 메서드
현재 UnorderedMap에 지정한 키가 들어 있는지 여부를 확인합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
bool HasKey(  
   K key  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 UnorderedMap 요소를 찾는 데 사용되는 키입니다. 유형의 `key` 형식 이름 *K*합니다.  
  
### <a name="return-value"></a>반환 값  
 키가 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  


## <a name="insert"></a>  UnorderedMap::Insert Method
지정한 키-값 쌍을 현재 UnorderedMap 개체에 추가합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
virtual bool Insert(  
   K key,   
   V value  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 키-값 쌍의 키 부분입니다. 유형의 `key` 형식 이름 *K*합니다.  
  
 `value`  
 키-값 쌍의 값 부분입니다. 유형의 `value` 형식 이름 *V*합니다.  
  
### <a name="return-value"></a>반환 값  
 현재 Map의 기존 요소 키가 `true`와 일치하고 해당 요소의 값 부분이 `key`로 설정된 경우 `value`입니다. 현재 Map의 기존 요소가 `false`와 일치하지 않고 `key` 및 `key` 매개 변수가 키-값 쌍으로 생성된 후 현재 UnorderedMap에 추가된 경우 `value`입니다.  
  


## <a name="lookup"></a>Unorderedmap:: Lookup 메서드
K 형식의 지정된 키와 연결된 V 형식의 값을 검색합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
V Lookup(  
   K key  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 UnorderedMap에서 요소를 찾는 데 사용되는 키입니다. 유형의 `key` 형식 이름 *K*합니다.  
  
### <a name="return-value"></a>반환 값  
 `key`와 쌍을 이루는 값입니다. 반환 값의 형식이 typename *V*합니다.  
  


## <a name="mapchanged"></a>Unorderedmap:: Mapchanged
맵에서 항목이 삽입되거나 제거될 때 발생합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
### <a name="property-valuereturn-value"></a>속성 값/반환 값  
 A [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) 에서 이벤트와 발생 한 변경의 종류를 발생 시킨 개체에 대 한 정보가 들어 있는입니다. 참고 항목 [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) 및 [CollectionChange 열거형](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx)합니다.  
  
## <a name="net-framework-equivalent"></a>.NET Framework의 해당 값  
 Windows 스토어 프로젝트는 앱 C# 또는 Visual Basic IMap\<K, V > IDictionary로\<K, V > 합니다.  
  


## <a name="remove"></a>Unorderedmap:: Remove 메서드
지정한 키-값 쌍을 UnorderedMap 개체에서 삭제합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
virtual void Remove(  
   K key);  
```  
  
### <a name="parameters"></a>매개 변수  
 `key`  
 키-값 쌍의 키 부분입니다. 유형의 `key` 형식 이름 *K*합니다.  
  


## <a name="size"></a>Unorderedmap:: Size 메서드
개수를 반환 [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) UnorderedMap에 있는 요소입니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>반환 값  
 UnorderedMap의 요소 수입니다.  
  


## <a name="ctor"></a>  UnorderedMap::UnorderedMap 생성자
UnorderedMap 클래스의 새 인스턴스를 초기화합니다.  
  
### <a name="syntax"></a>구문  
  
```cpp  
UnorderedMap();  
  
  explicit UnorderedMap(  
      size_t n  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  explicit UnorderedMap(  
      const std::unordered_map<K, V, H, P>& m  
      );  
  
  explicit UnorderedMap(  
      std::unordered_map<K, V, H, P>&& m  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  UnorderedMap(std::initializer_list<  
      std::pair<const K, V>> il  
      );  
  
  UnorderedMap(::std::initializer_list<  
      std::pair<const K, V>> il,  
      size_t n  
      );  
  
  UnorderedMap(  
      ::std::initializer_list< ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(::std::initializer_list<  
      ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
```  
  
### <a name="parameters"></a>매개 변수  
 `InIt`  
 현재 UnorderedMap의 형식 이름입니다.  
  
 `P`  
 같은지 여부를 확인하기 위해 두 키를 비교할 수 있는 함수 개체입니다. 이 매개 변수의 기본값은 [std:: equal_to\<K >](../standard-library/equal-to-struct.md)합니다.  
  
 `H`  
 키에 대한 해시 값을 생성하는 함수 개체입니다. 이 매개 변수의 기본값은 [클래스 1 해시](../standard-library/hash-class.md) 클래스는 지원 하 고 키 형식에 대 한 합니다.  
  
 `m`  
 대 한 참조 또는 [Lvalue 및 Rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) 에 [std:: unordered_map](../standard-library/unordered-map-class.md) 현재 UnorderedMap을 초기화 하는 데 사용 되는 합니다.  
  
 il  
 A [std:: initializer_list](../standard-library/initializer-list-class.md) 의 [std:: pair](../standard-library/pair-structure.md)map를 초기화 하는 데 사용할 개체입니다.  
  
 `first`  
 현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위에서 첫 번째 요소의 입력 반복기입니다.  
  
 `last`  
 현재 UnorderedMap을 초기화하는 데 사용되는 요소 범위 다음의 첫 번째 요소의 입력 반복기입니다.  
  


  
## <a name="see-also"></a>참고 항목  
 [플랫폼 Namespace](platform-namespace-c-cx.md)   
 [Platform:: collections Namespace](../cppcx/platform-collections-namespace.md)   
 [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)   
 [컬렉션](../cppcx/collections-c-cx.md)   
 [C + + Windows 런타임 구성 요소 만들기](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)