---
title: "Platform::Collections::VectorView 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView 클래스"
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Platform::Collections::VectorView 클래스
인덱스로 각각 액세스할 수 있는 순차 개체 컬렉션의 읽기 전용 보기를 나타냅니다. 템플릿 매개 변수로 지정된 컬렉션의 각 개체 형식입니다.  
  
## 구문  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### 매개 변수  
 `T`  
 `VectorView` 개체에 포함된 요소의 형식입니다.  
  
 `E`  
 `T` 형식의 값을 사용하여 같음을 테스트하기 위한 이진 조건자를 지정합니다. 기본값은 `std::equal_to<T>`입니다.  
  
## 설명  
 `VectorView` 클래스는 [Windows::Foundation::Collections::IVectorView\<T\>](http://go.microsoft.com/fwlink/p/?LinkId=262411) 인터페이스와 표준 템플릿 라이브러리 반복기에 대한 지원을 구현합니다.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[VectorView::VectorView 생성자](../cppcx/vectorview-vectorview-constructor.md)|VectorView 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[VectorView::First 메서드](../cppcx/vectorview-first-method.md)|VectorView의 첫 번째 요소를 지정하는 반복기를 반환합니다.|  
|[VectorView::GetAt 메서드](../cppcx/vectorview-getat-method.md)|지정된 인덱스가 나타내는 현재 VectorView의 요소를 검색합니다.|  
|[VectorView::GetMany 메서드](../cppcx/vectorview-getmany-method.md)|현재 VectorView에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.|  
|[VectorView::IndexOf 메서드](../cppcx/vectorview-indexof-method.md)|현재 VectorView에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.|  
|[VectorView::Size 메서드](../cppcx/vectorview-size-method.md)|현재 VectorView 개체의 요소 수를 반환합니다.|  
  
## 상속 계층  
 `VectorView`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+로 Windows Runtime 구성 요소 만들기](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)