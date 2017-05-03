---
title: "Platform::Collections::InputIterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator 클래스"
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::InputIterator 클래스
[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에서 파생된 컬렉션에 대한 표준 템플릿 라이브러리 InputIterator를 제공합니다.  
  
## 구문  
  
```  
template <  
   typename X  
>  
class InputIterator;  
```  
  
#### 매개 변수  
 `X`  
 InputIterator 템플릿 클래스의 형식 이름입니다.  
  
## 멤버  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|`difference_type`|포인터 차이\(ptrdiff\_t\)입니다.|  
|`iterator_category`|입력 반복기의 범주\(::std::input\_iterator\_tag\)입니다.|  
|`pointer`|`const` `X`에 대한 포인터입니다.|  
|`reference`|`const` `X`에 대한 참조입니다.|  
|`value_type`|`X` 형식 이름입니다.|  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[InputIterator::InputIterator 생성자](../cppcx/inputiterator-inputiterator-constructor.md)|InputIterator 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[InputIterator::operator\!\= 연산자](../cppcx/inputiterator-operator-inequality-operator.md)|현재 InputIterator가 지정된 InputIterator와 같지 않은지 여부를 나타냅니다.|  
|[InputIterator::operator\* 연산자](../cppcx/inputiterator-operator-decrementoperator.md)|현재 InputIterator가 지정하는 요소에 대한 참조를 검색합니다.|  
|[InputIterator::operator\+\+ 연산자](../cppcx/inputiterator-operator-increment-operator.md)|현재 InputIterator를 증가시킵니다.|  
|[InputIterator::operator\=\= 연산자](../cppcx/inputiterator-operator-equality-operator.md)|현재 InputIterator가 지정된 InputIterator와 같은지 여부를 나타냅니다.|  
|[InputIterator::operator\-\> 연산자](../cppcx/inputiterator-operator-arrow-operator.md)|현재 InputIterator가 참조하는 요소의 주소를 검색합니다.|  
  
## 상속 계층  
 `InputIterator`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)