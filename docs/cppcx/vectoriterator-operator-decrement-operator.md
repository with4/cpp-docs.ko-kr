---
title: "VectorIterator::operator-- 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator--"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-- 연산자"
ms.assetid: 650a3037-2984-4110-9d7c-cd3756e5f4b9
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-- 연산자
현재 VectorIterator를 감소시킵니다.  
  
## 구문  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(  
   int  
);  
```  
  
## 반환 값  
 첫 번째 구문은 현재 VectorIterator를 감소시킨 다음 반환합니다. 두 번째 구문은 현재 VectorIterator의 복사본을 반환한 다음 현재 VectorIterator를 감소시킵니다.  
  
## 설명  
 첫 번째 VectorIterator 구문은 현재 VectorIterator를 사전에 감소시킵니다.  
  
 두 번째 구문은 현재 VectorIterator를 사후에 감소시킵니다. 두 번째 구문의 `int` 형식은 실제 정수 연산자가 아니라 후위 감소 연산을 나타냅니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::VectorIterator 클래스](../cppcx/platform-collections-vectoriterator-class.md)