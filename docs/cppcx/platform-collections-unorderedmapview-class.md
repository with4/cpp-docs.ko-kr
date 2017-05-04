---
title: "Platform::Collections::UnorderedMapView 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView"
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Collections::UnorderedMapView 클래스
읽기 전용 보기를 키\/값 쌍의 컬렉션인 *맵*으로 나타냅니다.  
  
## 구문  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>  
>  
ref class UnorderedMapView sealed;  
```  
  
#### 매개 변수  
 `K`  
 키\/값 쌍의 키 형식입니다.  
  
 `V`  
 키\/값 쌍의 값 형식입니다.  
  
 `C`  
 같은지 확인하기 위해 두 키 값을 비교할 수 있는 함수 개체를 제공하는 형식입니다. 기본값은 [std::equal\_to\<K\>](../standard-library/equal-to-struct.md)입니다.  
  
## 설명  
 UnorderedMapView는 ABI\(응용 프로그램 이진 인터페이스\) 전반에서 전달되는 [Windows::Foundation::Collections::IMapView\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409) 인터페이스의 구체적 C\+\+ 구현입니다. 자세한 내용은 [컬렉션\(C\+\+\/CX\)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[UnorderedMapView::UnorderedMapView 생성자](../cppcx/unorderedmapview-unorderedmapview-constructor.md)|UnorderedMapView 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[UnorderedMapView::First 메서드](../cppcx/unorderedmapview-first-method.md)|맵 뷰의 첫 번째 요소로 초기화하는 반복기를 반환합니다.|  
|[UnorderedMapView::HasKey 메서드](../cppcx/unorderedmapview-haskey-method.md)|현재 UnorderedMapView에 지정한 키가 들어 있는지 여부를 확인합니다.|  
|[UnorderedMapView::Lookup 메서드](../cppcx/unorderedmapview-lookup-method.md)|현재 UnorderedMapView 개체의 지정된 키에 있는 요소를 검색합니다.|  
|[UnorderedMapView::Size 메서드](../cppcx/unorderedmapview-size-method.md)|현재 UnorderedMapView 개체의 요소 수를 반환합니다.|  
|[UnorderedMapView::Split 메서드](../cppcx/unorderedmapview-split-method.md)|원래 UnorderedMapView 개체를 두 개의 UnorderedMapView 개체로 분할합니다.|  
  
## 상속 계층  
 `UnorderedMapView`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections 네임스페이스](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)