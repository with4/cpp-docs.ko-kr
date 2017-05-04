---
title: "InputIterator::operator++ 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator++ 연산자"
ms.assetid: 50781585-7a12-4f02-bff8-68fe0adf0693
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator++ 연산자
현재 InputIterator를 증가시킵니다.  
  
## 구문  
  
```  
  
InputIterator& operator++();  
  
InputIterator operator++(  
   int  
);  
```  
  
## 반환 값  
 첫 번째 구문은 현재 InputIterator를 증가시킨 다음 반환합니다. 두 번째 구문은 현재 InputIterator의 복사본을 반환한 다음 현재 InputIterator를 증가시킵니다.  
  
## 설명  
 첫 번째 InputIterator 구문은 현재 InputIterator를 사전에 증가시킵니다.  
  
 두 번째 구문은 현재 InputIterator를 사후에 증가시킵니다. 두 번째 구문의 `int` 형식은 실제 정수 연산자가 아니라 후위 증가 연산을 나타냅니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::InputIterator 클래스](../cppcx/platform-collections-inputiterator-class.md)