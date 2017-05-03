---
title: "Platform::Collections::Vector 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector 클래스(C++/Cx)"
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# Platform::Collections::Vector 클래스
개별적으로 인덱스에 의해 액세스될 수 있는 개체의 순차적인 컬렉션을 나타냅니다.  
  
## 구문  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### 매개 변수  
 `T`  
 Vector 개체에 포함된 요소의 형식입니다.  
  
 `E`  
 `T` 형식의 값을 사용하여 같음을 테스트하기 위한 이진 조건자를 지정합니다. 기본값은 `std::equal_to<T>`입니다.  
  
## 설명  
 허용되는 형식은 다음과 같습니다.  
  
1.  정수  
  
2.  인터페이스 클래스 ^  
  
3.  public ref 클래스 ^  
  
4.  value struct  
  
5.  public enum 클래스  
  
 Vector 클래스는 [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) 인터페이스의 구체적인 C\+\+ 구현입니다.  
  
 공용 반환 값 또는 매개 변수에서 Vector 형식을 사용하려고 하면 컴파일러 오류 C3986이 발생합니다. 매개 변수나 반환 값 형식을 [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410)로 변경하여 오류를 수정할 수 있습니다. 자세한 내용은 [컬렉션\(C\+\+\/CX\)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[Vector::Vector 생성자](../cppcx/vector-vector-constructor.md)|Vector 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[Vector::Append 메서드](../cppcx/vector-append-method.md)|현재 Vector의 마지막 항목 다음에 지정된 항목을 삽입합니다.|  
|[Vector::Clear 메서드](../cppcx/vector-clear-method.md)|현재 Vector의 모든 요소를 삭제합니다.|  
|[Vector::First 메서드](../cppcx/vector-first-method.md)|Vector의 첫 번째 요소를 지정하는 반복기를 반환합니다.|  
|[Vector::GetAt 메서드](../cppcx/vector-getat-method.md)|지정된 인덱스로 식별되는 현재 Vector의 요소를 검색합니다.|  
|[Vector::GetMany 메서드](../cppcx/vector-getmany-method.md)|현재 Vector에서 지정된 인덱스부터 시작하여 일련의 항목을 검색합니다.|  
|[Vector::GetView 메서드](../cppcx/vector-getview-method.md)|Vector의 읽기 전용 보기, 즉 [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md)를 반환합니다.|  
|[Vector::IndexOf 메서드](../cppcx/vector-indexof-method.md)|현재 Vector에서 지정한 항목을 검색하고 있는 경우 항목의 인덱스를 반환합니다.|  
|[Vector::InsertAt 메서드](../cppcx/vector-insertat-method.md)|현재 Vector에서 지정된 인덱스로 식별되는 요소 뒤에 지정된 항목을 삽입합니다.|  
|[Vector::ReplaceAll 메서드](../cppcx/vector-replaceall-method.md)|현재 Vector에서 요소를 삭제한 다음 지정된 배열의 요소를 삽입합니다.|  
|[Vector::RemoveAt 메서드](../cppcx/vector-removeat-method.md)|현재 Vector에서 지정된 인덱스로 식별되는 요소를 삭제합니다.|  
|[Vector::RemoveAtEnd 메서드](../cppcx/vector-removeatend-method.md)|현재 Vector의 끝에 있는 요소를 삭제합니다.|  
|[Vector::SetAt 메서드](../cppcx/vector-setat-method.md)|현재 Vector에서 지정된 인덱스로 식별되는 요소에 지정된 값을 할당합니다.|  
|[Vector::Size 메서드](../cppcx/vector-size-method.md)|현재 Vector 개체의 요소 수를 반환합니다.|  
  
### 이벤트  
  
|||  
|-|-|  
|이름|설명|  
|이벤트 [Windows::Foundation::Collection::VectorChangedEventHandler\<T\>^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Vector가 변경될 때 발생합니다.|  
  
## 상속 계층  
 `Vector`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [C\+\+로 Windows Runtime 구성 요소 만들기](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)