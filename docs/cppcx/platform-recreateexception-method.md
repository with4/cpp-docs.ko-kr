---
title: "Platform::ReCreateException 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ReCreateException"
dev_langs: 
  - "C++"
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ReCreateException 메서드
이 메서드는 내부 전용이며 사용자 코드에서는 사용되지 않습니다. 그 대신 [Exception::CreateException 메서드](../cppcx/exception-createexception-method.md)를 사용하십시오.  
  
## 구문  
  
```vb  
static Exception^ ReCreateException(int hr)  
```  
  
#### 매개 변수  
  
## 속성 값\/반환 값  
 지정된 HRESULT에 따라 새 Platform::Exception^을 반환합니다.  
  
## 해당 .NET Framework 항목  
  
## 요구 사항