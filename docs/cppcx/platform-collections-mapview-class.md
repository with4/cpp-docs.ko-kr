---
title: "Platform::Collections::MapView 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView 클래스"
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Collections::MapView 클래스
읽기 전용 보기를 키\/값 쌍의 컬렉션인 *맵*으로 나타냅니다.  
  
## 구문  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>  
>  
ref class MapView sealed;  
```  
  
#### 매개 변수  
 `K`  
 키\/값 쌍의 키 형식입니다.  
  
 `V`  
 키\/값 쌍의 값 형식입니다.  
  
 `C`  
 두 요소 값을 정렬 키로 비교하여 MapView에서 해당 상대 순서를 확인할 수 있는 함수 개체를 제공하는 형식입니다. 기본값은 [::std::less\<K\>](../standard-library/less-struct.md)입니다.  
  
## 설명  
 MapView는 ABI\(응용 프로그램 이진 인터페이스\) 전반에서 전달되는 [Windows::Foundation::Collections::IMapView \<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409) 인터페이스의 구체적 C\+\+ 구현입니다. 자세한 내용은 [컬렉션\(C\+\+\/CX\)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[MapView::MapView 생성자](../cppcx/mapview-mapview-constructor.md)|MapView 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[MapView::First 메서드](../cppcx/mapview-first-method.md)|맵 뷰의 첫 번째 요소로 초기화하는 반복기를 반환합니다.|  
|[MapView::HasKey 메서드](../cppcx/mapview-haskey-method.md)|현재 MapView에 지정한 키가 들어 있는지 여부를 확인합니다.|  
|[MapView::Lookup 메서드](../cppcx/mapview-lookup-method.md)|현재 MapView 개체의 지정된 키에 있는 요소를 검색합니다.|  
|[MapView::Size 메서드](../cppcx/mapview-size-method.md)|현재 MapView 개체의 요소 수를 반환합니다.|  
|[MapView::Split 메서드](../cppcx/mapview-split-method.md)|원래 MapView 개체를 두 개의 MapView 개체로 분할합니다.|  
  
## 상속 계층  
 `MapView`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)