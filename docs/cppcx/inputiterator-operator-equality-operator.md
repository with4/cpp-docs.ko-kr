---
title: "InputIterator::operator== 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator== 연산자"
ms.assetid: 84f1b69a-77b9-467c-ad1a-2fe8a7c3009e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator== 연산자
현재 InputIterator가 지정된 InputIterator와 같은지 여부를 나타냅니다.  
  
## 구문  
  
```  
bool operator==(  
   const InputIterator& other  
) const;  
```  
  
#### 매개 변수  
 `other`  
 다른 InputIterator입니다.  
  
## 반환 값  
 현재 InputIterator가 `true`와 같으면 `other`이고, 같으면 `false`입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::InputIterator 클래스](../cppcx/platform-collections-inputiterator-class.md)