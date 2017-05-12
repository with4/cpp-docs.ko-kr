---
title: "Platform::Collections::BackInsertIterator 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator 클래스"
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Collections::BackInsertIterator 클래스
요소를 덮어쓰지 않고 순차 컬렉션의 백 엔드에 삽입하는 반복기를 나타냅니다.  
  
## 구문  
  
```  
template <  
   typename T  
>  
class BackInsertIterator : public ::std::iterator< ::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### 매개 변수  
 `T`  
 현재 컬렉션에 있는 항목의 형식입니다.  
  
## 설명  
 BackInsertIterator 클래스는 [back\_insert\_iterator 클래스](../standard-library/back-insert-iterator-class.md)에 필요한 규칙을 구현합니다.  
  
## 멤버  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[BackInsertIterator::BackInsertIterator 생성자](../cppcx/backinsertiterator-backinsertiterator-constructor.md)|BackInsertIterator 클래스의 새 인스턴스를 초기화합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[BackInsertIterator::operator\* 연산자](../cppcx/backinsertiterator-operator-dereference-operator.md)|현재 BackInsertIterator에 대한 참조를 검색합니다.|  
|[BackInsertIterator::operator\+\+ 연산자](../cppcx/backinsertiterator-operator-increment-operator.md)|현재 BackInsertIterator에 대한 참조를 반환합니다. 반복기는 수정되지 않습니다.|  
|[BackInsertIterator::operator\= 연산자](../cppcx/backinsertiterator-operator-assign-operator.md)|지정된 개체를 현재 순차 컬렉션의 끝에 추가합니다.|  
  
## 상속 계층  
 `BackInsertIterator`  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [\(NOTINBUILD\) Platform 네임스페이스](http://msdn.microsoft.com/ko-kr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)