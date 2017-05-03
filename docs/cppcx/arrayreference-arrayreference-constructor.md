---
title: "ArrayReference::ArrayReference 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::ArrayReference"
dev_langs: 
  - "C++"
ms.assetid: 9fc7dfcf-47af-40ba-a697-da476fb90efc
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# ArrayReference::ArrayReference 생성자
[Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) 클래스의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
ArrayReference(TArg* ataArg, unsigned int sizeArg, bool needsInitArg = false);  
ArrayReference(ArrayReference&& otherArg)  
  
```  
  
#### 매개 변수  
 `dataArg`  
 배열 데이터에 대한 포인터입니다.  
  
 `sizeArg`  
 소스 배열의 요소 수입니다.  
  
 `otherArg`  
 새 인스턴스 초기화를 위해 해당 데이터가 이동될 `ArrayReference` 개체입니다.  
  
## 설명  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::ArrayReference 클래스](../cppcx/platform-arrayreference-class.md)   
 [Array 및 WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)