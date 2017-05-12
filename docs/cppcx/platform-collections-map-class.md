---
title: "Platform::Collections::Map 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map 클래스(C++/Cx)"
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: 19
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 19
---
# Platform::Collections::Map 클래스
키\/값 쌍의 컬렉션인 *맵*을 나타냅니다.  
  
## 구문  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>  
ref class Map sealed;  
```  
  
#### 매개 변수  
 `K`  
 키\/값 쌍의 키 형식입니다.  
  
 `V`  
 키\/값 쌍의 값 형식입니다.  
  
 `C`  
 두 요소 값을 정렬 키로 비교하여 맵에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본값은 [std::less\<K\>](../standard-library/less-struct.md)입니다.  
  
 \_\_is\_valid\_winrt\_type\(\)  
 K 및 V 형식의 유효성을 검사하고 해당 형식을 Map에 저장할 수 없을 경우 친숙한 오류 메시지를 제공하는 컴파일러 생성 함수입니다.  
  
## 설명  
 허용되는 형식은 다음과 같습니다.  
  
-   정수  
  
-   인터페이스 클래스 ^  
  
-   public ref 클래스 ^  
  
-   value struct  
  
-   public enum 클래스  
  
 Map은 기본적으로 [std::map](../standard-library/map-class.md)에 대한 래퍼입니다. Map은 공용 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 인터페이스 전반에서 전달되는 [Windows::Foundation::Collections::IMap\<Windows::Foundation::Collections::IKeyValuePair\<K,V\>\>](http://go.microsoft.com/fwlink/p/?LinkId=262408) 및 [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) 형식의 구체적인 C\+\+ 구현입니다. 공용 반환 값 또는 매개 변수에서 `Platform::Collections::Map` 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수 또는 반환 값의 형식을  [Windows::Foundation::Collections::IMap\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262408)으로 변경하여 오류를 수정할 수 있습니다.  
  
 자세한 내용은 [컬렉션](../cppcx/collections-c-cx.md)을 참조하세요.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[Map::Map 생성자](../cppcx/map-map-constructor.md)|Map 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[Map::Clear 메서드](../cppcx/map-clear-method.md)|현재 Map 개체에서 모든 키\/값 쌍을 제거합니다.|  
|[Map::First 메서드](../cppcx/map-first-method.md)|맵의 첫 번째 요소를 지정하는 반복기를 반환합니다.|  
|[Map::GetView 메서드](../cppcx/map-getview-method.md)|현재 Map의 읽기 전용 보기, 즉 [Platform::Collections::MapView 클래스](../cppcx/platform-collections-mapview-class.md)를 반환합니다.|  
|[Map::HasKey 메서드](../cppcx/map-haskey-method.md)|현재 Map에 지정한 키가 들어 있는지 여부를 확인합니다.|  
|[Map::Insert 메서드](../cppcx/map-insert-method.md)|지정한 키\/값 쌍을 현재 Map 개체에 추가합니다.|  
|[Map::Lookup 메서드](../cppcx/map-lookup-method.md)|현재 Map 개체의 지정된 키에 있는 요소를 검색합니다.|  
|[Map::Remove 메서드](../cppcx/map-remove-method.md)|지정한 키\/값 쌍을 현재 Map 개체에서 삭제합니다.|  
|[Map::Size 메서드](../cppcx/map-size-method.md)|현재 Map 개체의 요소 수를 반환합니다.|  
  
### 이벤트  
  
|||  
|-|-|  
|이름|설명|  
|[Map::MapChanged 이벤트](../cppcx/map-mapchanged-event.md) `event`|Map이 변경될 때 발생합니다.|  
  
## 상속 계층  
 `Map`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+로 Windows Runtime 구성 요소 만들기](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)