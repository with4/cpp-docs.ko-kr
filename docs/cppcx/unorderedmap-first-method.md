---
title: "UnorderedMap::First 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::First"
ms.assetid: 915e771a-cec1-4905-8ecb-76501f63c143
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::First 메서드
순서가 지정되지 않은 맵의 첫 번째 [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) 요소를 지정하는 반복기를 반환합니다.  
  
## 구문  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## 반환 값  
 맵의 첫 번째 요소를 지정하는 반복기입니다.  
  
## 설명  
 First\(\)에서 반환된 반복기를 보유하는 편리한 방법은 [auto](../Topic/auto%20\(C++\).md) 형식 추론 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. 예를 들어, `auto x = myUnorderedMap->First();`을 입력합니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Platform::Collections  
  
## 참고 항목  
 [Platform::Collections::UnorderedMap 클래스](../cppcx/platform-collections-unorderedmap-class.md)   
 [컬렉션](../cppcx/collections-c-cx.md)