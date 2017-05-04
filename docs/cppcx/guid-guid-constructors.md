---
title: "Guid::Guid 생성자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Guid::Guid"
  - "Guid::Guid"
ms.assetid: dfa4dcad-1c3b-481f-9f60-05141b9788d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Guid::Guid 생성자
Guid 구조체의 새 인스턴스를 초기화합니다.  
  
## 구문  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  
);  
  
    Guid(   
        GUID m  
);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n  
);  
```  
  
#### 매개 변수  
 `a`  
 GUID의 처음 4바이트입니다.  
  
 `b`  
 GUID의 다음 2바이트입니다.  
  
 `c`  
 GUID의 다음 2바이트입니다.  
  
 `d`  
 GUID의 다음 바이트입니다.  
  
 `e`  
 GUID의 다음 바이트입니다.  
  
 `f`  
 GUID의 다음 바이트입니다.  
  
 `g`  
 GUID의 다음 바이트입니다.  
  
 `h`  
 GUID의 다음 바이트입니다.  
  
 `i`  
 GUID의 다음 바이트입니다.  
  
 `j`  
 GUID의 다음 바이트입니다.  
  
 `k`  
 GUID의 다음 바이트입니다.  
  
 `m`  
 .으로 정의된 GUID입니다.  
  
 `n`  
 GUID의 나머지 8바이트입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::Guid 값 클래스](../cppcx/platform-guid-value-class.md)