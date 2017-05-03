---
title: "Platform::Collections::UnorderedMap 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap"
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Collections::UnorderedMap 클래스
키\-값 쌍의 컬렉션인 순서가 지정되지 않은 *맵*을 나타냅니다.  
  
## 구문  
  
```scr  
template <  
   typename K,  
   typename V,  
   typename C = std::equal_to<K>  
>  
ref class Map sealed;  
```  
  
#### 매개 변수  
 `K`  
 키\/값 쌍의 키 형식입니다.  
  
 `V`  
 키\/값 쌍의 값 형식입니다.  
  
 `C`  
 두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본값은 [std::equal\_to\<K\>](../standard-library/equal-to-struct.md)입니다.  
  
## 설명  
 허용되는 형식은 다음과 같습니다.  
  
-   정수  
  
-   인터페이스 클래스 ^  
  
-   public ref 클래스 ^  
  
-   value struct  
  
-   public enum 클래스  
  
 UnorderedMap은 기본적으로 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식의 저장을 지원하는 [std::unordered\_map](../standard-library/unordered-map-class.md)에 대한 래퍼입니다. 이는 공용 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 인터페이스 전반에서 전달되는 [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) 및 [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) 형식의 구체적 구현입니다. 공용 반환 값 또는 매개 변수에서 Platform::Collections::UnorderedMap 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수나 반환 값 형식을 [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408)으로 변경하여 오류를 수정할 수 있습니다.  
  
 자세한 내용은 [컬렉션](../cppcx/collections-c-cx.md)을 참조하세요.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|UnorderedMap::UnorderedMap 생성자|Map 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[UnorderedMap::Clear 메서드](../cppcx/unorderedmap-clear-method.md)|현재 Map 개체에서 모든 키\/값 쌍을 제거합니다.|  
|[UnorderedMap::First 메서드](../cppcx/unorderedmap-first-method.md)|맵의 첫 번째 요소를 지정하는 반복기를 반환합니다.|  
|[UnorderedMap::GetView 메서드](../cppcx/unorderedmap-getview-method.md)|현재 Map의 읽기 전용 뷰, 즉 Platform::Collections::UnorderedMapView 클래스를 반환합니다.|  
|[UnorderedMap::HasKey 메서드](../cppcx/unorderedmap-haskey-method.md)|현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.|  
|[UnorderedMap::Insert 메서드](../cppcx/unorderedmap-insert-method.md)|지정한 키\/값 쌍을 현재 Map 개체에 추가합니다.|  
|[UnorderedMap::Lookup 메서드](../cppcx/unorderedmap-lookup-method.md)|현재 Map 개체의 지정된 키에 있는 요소를 검색합니다.|  
|[UnorderedMap::Remove 메서드](../cppcx/unorderedmap-remove-method.md)|지정한 키\/값 쌍을 현재 Map 개체에서 삭제합니다.|  
|[UnorderedMap::Size 메서드](../cppcx/unorderedmap-size-method.md)|현재 Map 개체의 요소 수를 반환합니다.|  
  
### 이벤트  
  
|||  
|-|-|  
|이름|설명|  
|[Map::MapChanged 이벤트](../cppcx/map-mapchanged-event.md) `event`|Map이 변경될 때 발생합니다.|  
  
## 상속 계층  
 `UnorderedMap`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Platform::Collections 네임스페이스](../cppcx/platform-collections-namespace.md)   
 [Platform::Collections::Map 클래스](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapView 클래스](../cppcx/platform-collections-unorderedmapview-class.md)   
 [컬렉션](../cppcx/collections-c-cx.md)   
 [C\+\+로 Windows Runtime 구성 요소 만들기](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)